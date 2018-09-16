---
title: "Revelの親コントローラを作成する"
date: 2016-12-12T10:35:50+09:00
draft: false
tags:
- golang
- revel
<!-- thumbnailImagePosition: left -->
<!-- thumbnailImage: //d1u9biwaxjngwg.cloudfront.net/cover-image-showcase/city-750.jpg -->
<!-- coverImage: //d1u9biwaxjngwg.cloudfront.net/cover-image-showcase/city.jpg -->
<!-- metaAlignment: center -->
<!-- coverMeta: out -->
---

親コントローラ生成について
親コントローラ（ドキュメントではExtending the Controllerとなっているが）は下記のドキュメントのように作成すると良い。

<!--more-->

https://revel.github.io/quickstart/controllers.html#extending-the-controller

{{< highlight go "linenos=inline" >}}
type (
	BaseController struct {
		*revel.Controller
	}
)
type (
	MyController struct {
		BaseController
	}
)
{{< / highlight >}}

このとき、

> Note in the MyController the BaseController reference is NOT a pointers.

> 訳 : MyControllerでは、BaseController参照はポインタではありません

とのことなので注意。


またこのとき、ファイルを分けることもパッケージを分けることも可能なので、

controllers/core/baseController.go

{{< highlight go "linenos=inline" >}}
package core

import (
	"github.com/revel/revel"
)

type (
	BaseController struct {
		*revel.Controller
	}
)
{{< / highlight >}}

controllers/myController.go

{{< highlight go "linenos=inline" >}}
package controllers

import (
	"github.com/revel/revel"
	"path/to/controllers/core"
)

type (
	MyController struct {
		BaseController
	}
)

{{< / highlight >}}


という形でもOK。
