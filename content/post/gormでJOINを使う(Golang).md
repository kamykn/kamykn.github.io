---
title: "gormでJOINを使う(Golang)"
date: 2016-12-19T16:21:11+09:00
draft: false
tags:
- golang
- gorm
<!-- thumbnailImagePosition: left -->
<!-- thumbnailImage: //d1u9biwaxjngwg.cloudfront.net/cover-image-showcase/city-750.jpg -->
<!-- coverImage: //d1u9biwaxjngwg.cloudfront.net/cover-image-showcase/city.jpg -->
<!-- metaAlignment: center -->
<!-- coverMeta: out -->
---

今回は、gormで返り値にJoinされる方のテーブルの値は取れているが、Joinする方のテーブルの値が取れていないときのTips。
結論から言うと、JOINを使う場合にはSelect()を指定することと、変数の型に注意。  

<!--more-->

# gormでJoinを使うときの注意
当初はこんな感じで記述して取れていなかった。
{{< highlight go "linenos=inline" >}}
commentList := []Comment{}
db.Where("entry_id = ?", entryID).Joins("INNER JOIN accounts on accounts.id = comments.account_id").Find(&commentList)
{{< / highlight >}}


## Findで指定している変数の型がこのままではダメそうなことに気づく
ということで下記のように修正。それでもダメだった。

{{< highlight go "linenos=inline" >}}
type CommentJoinsAccount struct {
    Comment
    Account
}

commentList := []CommentJoinsAccount{}
db.Table("comments").Joins("INNER JOIN accounts ON accounts.id = comments.account_id").Where("entry_id = ?", entryID).Order("id desc").Limit(limit).Scan(&commentList)
{{< / highlight >}}
※ Find()でテーブル指定していたのをScan()に変更したので、Table()を追加。  
※ そしてScan()だとソフトデリートが自動化されないのね…『.Where("comments.deleted_at IS NULL")』を追加しました


## ドキュメントの方ではSelectをわざわざ指定していることに気づく
[http://jinzhu.me/gorm/crud.html#joins:title]  
Joinする方のテーブルのSelectを指定するのが必須だったみたい（しかもカラムも指定）。


{{< highlight go "linenos=inline" >}}
type CommentJoinsAccount struct {
    Comment
    Account
}

commentList := []CommentJoinsAccount{}
db.Table("comments").Select("comments.*, accounts.name, accounts.icon").Joins("INNER JOIN accounts ON accounts.id = comments.account_id").Where("entry_id = ?", entryID).Order("id desc").Limit(limit).Scan(&commentList)
{{< / highlight >}}

このとき、
{{< highlight go "linenos=inline" >}}
.Select("comments.*, accounts.*")
{{< / highlight >}}
でもダメみたいです。
