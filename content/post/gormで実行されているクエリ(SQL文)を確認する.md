
---
title: "gormでJOINを使う(Golang)"
date: 2016-12-19T16:34:51+09:00
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


下記のように実行しているgormの裏側で実行されているクエリが知りたい場合には…

{{< highlight go "linenos=inline" >}}
db.Where("id = ?", accountID).Find(&account)
{{< / highlight >}}

<!--more-->


Debug()を追加してあげると良い。
{{< highlight go "linenos=inline" >}}
db.Debug().Where("id = ?", accountID).Find(&account)
{{< / highlight >}}
