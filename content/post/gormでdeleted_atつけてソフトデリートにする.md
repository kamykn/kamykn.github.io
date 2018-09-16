---
title: "Gormでdeleted_atつけてソフトデリートにする"
date: 2016-12-11T00:05:26+09:00
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


言語での開発ではモデル周りはgorm使っています。  
ソフトデリート利用するときにちょっとハマって、デフォルトで0000-00-00 00:00:00が入ってしまう人のためのTips。

<!--more-->

# 以下のように記述するとOK

{{< highlight go "linenos=inline" >}}

package models

import (
    "time"
	)

type Table struct {
	ID      int
	CreatedAt       time.Time
	UpdatedAt       time.Time
	DeletedAt       *time.Time
}

{{< / highlight >}}

DeletedAtだけ*time.Timeになることに注意。

デフォルトでカラムにnull以外が入っているとgormのソフトデリート的には削除済み扱いになってしまうみたいです。
