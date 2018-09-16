---
title: "返り値で型指定するDuck Typing"
date: 2016-12-16T01:11:27+09:00
draft: false
tags:
- golang
<!-- thumbnailImagePosition: left -->
<!-- thumbnailImage: //d1u9biwaxjngwg.cloudfront.net/cover-image-showcase/city-750.jpg -->
<!-- coverImage: //d1u9biwaxjngwg.cloudfront.net/cover-image-showcase/city.jpg -->
<!-- metaAlignment: center -->
<!-- coverMeta: out -->
---

Go言語では様々な形でダックタイピングが可能です。
今回はGo言語で利用可能な返り値の型指定を利用する例を紹介します。

<!--more-->

{{< highlight go "linenos=inline" >}}
``go
package main

import (
	"fmt"
	"errors"
)

func main() {
	robot, err1 := GetDuck("robot")
	if err1 == nil {
		robot.Quack()
	}
	
	human, err2 := GetDuck("human")
	if err2 == nil {
		human.Quack()
	}
}

func GetDuck (ducktype string) (Duck, error) {
	if ducktype == "human" {
		return Human{}, nil
	} else if ducktype == "robot" {
		return Robot{}, nil
	}
	
	return nil, errors.New("正しいタイプを選んでね")
}

type Duck interface {
	Quack()
}

type Robot struct {}

func (r Robot) Quack () {
	fmt.Println("Q-U-A-C-K")
}

type Human struct {}

func (h Human) Quack () {
	fmt.Println("がーがー")
}
{{< / highlight >}}

GetDuck()関数を通して構造体を取得することで、Human型とRobot型をDuck型として扱う事ができました。

個人的に最近使ったケースはOAuth1とOAuth2の認証部分を別々の構造体として実装し、呼び出し部分でGetDuck()の関数のようにOAuth型として取得し、コントローラ側から見たときにOAuth型としてOAuthのバージョンを意識しなくても良いような実装を行ってみたりしていました。
