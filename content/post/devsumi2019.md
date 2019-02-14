---
title: "Devsumi2019"
date: 2019-02-14T11:01:03+09:00
tags:
- event
keywords:
- Developer Summit 2019
- event
thumbnailImagePosition: left
thumbnailImage: /images/post/2019-02-14/01.jpg
---

デブサミ1日目に行ってきました！初デブサミ、初雅叙園！  
今回は引き続きKubernetesの話とYahooさんのフロントエンドとかがお目当てです。

<!--more-->
![デブサミ2019](/images/post/2019-02-14/01.jpg "デブサミ2019")
(こちらの画像は1日目の12:50頃の言語投票状況)

今回もいくつかセッション聞いてきたのですが、いくつかピックアップしてログとして残しておきます。
(なお、こちらは14日の分の記事で、15日は私は通常通り業務に戻るので明日は参加しない予定になります。)

# GitHub Actions
Takahumi Ikeda さん  
Solutions Engineer GitHub  
github: ikeike443  

## ソフトウェア開発の障壁
障壁は下がったがツールが増えすぎた  
いろいろなソフトくっつける作業がエンジニアのメインのタスクではない  
これをGitHubActionで変えたい

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">世の中にはツール増えすぎてるの図<br> <a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a> <a href="https://twitter.com/hashtag/devsumiA?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiA</a> <a href="https://t.co/wVJWruYY29">pic.twitter.com/wVJWruYY29</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095868972564529152?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


## Cloud Native Landscape
ツール増えすぎてる  
モジュール化されるべきで、簡単に取捨選択できるべき

## GitHub Actions
- Actionsの実態はDockerFileらしい
- コンテナ技術ベース
- ワークフロー as Code

## 手順
### Actionの作成
- Action を格納するリポジトリを作る
- Dockerfileを作る
- entrypoint.sh

### ワークフローの作成
- GUIで流れを紐づけ
- PullRequest作って実行してみる
- 暫くすると実行されて結果が見れる

### ワークフローの変更
- 最初は上とおんなじ感じ
- 普通のPullRequestと同じ感じで変更できる
- 結果を見る


## デモ
- EKS用意してください
- (ちょっと横道にそれて)シークレットなAPIの紹介
	- octocatの名言AA
		- https://api.github.com/octocat
		- <blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">Githubの隠れAPIとのこと <a href="https://t.co/NN3qYStiMC">https://t.co/NN3qYStiMC</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095877004526641154?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

- リッチGUIで現在どれが処理されているかわかる

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">結構リッチなUIだなぁ<br> <a href="https://twitter.com/hashtag/devsumiA?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiA</a>  <a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a> <a href="https://t.co/skULs8FG2n">pic.twitter.com/skULs8FG2n</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095875393796489217?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


## 現状想定している仕様
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">Github Actions の現状の仕様<br> <a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a>  <a href="https://twitter.com/hashtag/devsumiA?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiA</a> <a href="https://t.co/G7buthz30l">pic.twitter.com/G7buthz30l</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095873010626527233?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-conversation="none" data-lang="ja"><p lang="ja" dir="ltr">もう少しあった <a href="https://t.co/GtGYYXXEOc">pic.twitter.com/GtGYYXXEOc</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095873223516770304?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-conversation="none" data-lang="ja"><p lang="ja" dir="ltr">βなので変わる可能性あるので、使う際には最新のドキュメント読んでね！<br>とのこと</p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095873456082567168?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


## Callback
### Repository Dispatch
外に任意にトリガーできるイベント

## 情報を得るには
GithubActionsというOrganizationがあるので見てね  
マーケットプレースにAction登録できる  
awesome actionsという個人のブランチがある  

## まとめ
ワークフローはモジュラー化される。  
あと、デモで使っていたinsomnia というAPI実行ツールが気になりました。
https://insomnia.rest/

# Cloud Native 時代におけるDocker / Kubernetesによる開発
CyberAgent adtech studio  
Masaya Aoyamaさん  

資料はこちらです  
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">これからデブサミで登壇します。たくさん来ていただいてありがたみ。<br>「SHARE YOUR FUN」がテーマらしいので、ひとこと。<br>Kubernetes だいすき。<br><br>「Cloud Native 時代における Docker / Kubernetes による開発」<a href="https://t.co/jRTvaTh5Aq">https://t.co/jRTvaTh5Aq</a><a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a> <a href="https://twitter.com/hashtag/devsumiA?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiA</a></p>&mdash; MasayaAoyama（青山 真也） (@amsy810) <a href="https://twitter.com/amsy810/status/1095896443141799941?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">インスタ映えするKubernetesクラスタの図<br><br>🤔<br> <a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a>  <a href="https://twitter.com/hashtag/devsumiA?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiA</a> <a href="https://t.co/IFVhTgjygG">pic.twitter.com/IFVhTgjygG</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095897382099681281?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
やばい人北。

## CloudNativeに適したアーキテクチャー
マイクロサービス

- マイクロサービスごとに技術選定
- 大規模な開発(部門ごとの専門化)
- デプロイ
- スケーチング
- 障害が全体に波及しづらい

##  Service Mesh Architecture
500+のマイクロサービスを監視するのは難しい。

- Microservice間通信のモニタリング(メトリクス収集)
- Traffic shifting (Canary release)
- 従来の青瓜ケーション側で制御していた機能を分離
- 開発者はアプリケーションのロジックのみに集中できる

### Srvice Meshを利用することで
Microservice間の  
├可観測性を確保  
├柔軟な通信の制御  
└暗号化  

### Dockerコンテナの起動とは
新たなレイヤを作成して起動すること  

- 新たなread write可能なレイヤが追加されただけのイメージ

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">今日のデブサミのKubernetesスライドの、Dockerfileの内容に対応してDockerコンテナの中のレイヤが増えていくイメージが、すごくなるほど感があった。<a href="https://t.co/CdGGpR6KAR">https://t.co/CdGGpR6KAR</a> <a href="https://t.co/CeSUmx8LaF">pic.twitter.com/CeSUmx8LaF</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1096076501747851265?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

DockerfileのRUNとかの単位でハッシュを持っているのは、分離したレイヤが作られているから。  
ベースのimageにそれらのレイヤが適用されていってbuildされているということなのか・・・！  
そしてコンテナ起動は最後のReadWriteなレイヤが追加されるということだと。なるほど。

## kubernetes
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">他のオーケストレーションツールではなく、kubernetesが支持されるのはコンテナ技術の標準に沿っているから <a href="https://twitter.com/hashtag/devsumiA?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiA</a> <a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a> <a href="https://t.co/IIG07V8hQ3">pic.twitter.com/IIG07V8hQ3</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095902310629163008?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### ReplicaSetとSelf-Healing
- ReplicaSetではコンテナのReplica数を維持し続ける
  - = Node障害等で コンテナが不足した場合、別のNode上で起動

### ReplicaSetとRolling Update
- ロードバランサからの除外
- コンテナイメージのアップデート
- ロードバランサへの追加

Developerはマニフェストを変更するだけ  

- KubernetesはGoogkeが社内で数年使っていた
  - コンテナクラスタマネージャBorgをベースにOSS化したもの
  - 様々なワークロードへの対応洗練化された自動化、拡張性
- 抽象化されており、ネットワークの操作などもYAMLを書くだけ
  - OPSだけが使うものではなくDEVも使うもの


## 分散システムとしてのKubernetes
### Control Loop 
- 現在の状態を観測
- 現在の状態と理想状態を比較
- 差分に対処する処理を実施

  
**例: エアコンならば**

- 30度
- 30度との差
- 上げる

ReplicaSetなどの基本的なリソースも同様

## Custom Resource Definition
マニフェストの登録 → マネージドサービスへの操作  
例: Kubernetes上にPodを起動してQueueクラスタを展開  

## CI/CD
GitOps  
Single Source of Truece (私はVue.jsで初めてこの言葉に出会いましたが、Vue.js以外でも通用する言葉なんですね)  


## 攻めた銀行
**Monzo bank** https://monzo.com/   
Kubernetes + linkerd(Service Mesh)


## まとめ
これ買うと良い・・・！  
https://www.amazon.co.jp/dp/4295004804/ref=asc_df_42950048042585734/?tag=jpgo-22&creative=9303&creativeASIN=4295004804&linkCode=df0&hvadid=295704876452&hvpos=1o1&hvnetw=g&hvrand=17930246126622535468&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1009300&hvtargid=pla-525497287608&th=1&psc=1


# ヤフー株式会社におけるフロントエンドの取り組み
- 向井 咲人さん
- 平山 涼也さん
- 森本 恭平さん


## 登壇に至った経緯
ヤフーのwebフロント絵hんどの技術選定についてテックブログを書いた  
https://techblog.yahoo.co.jp/advent-calendar-2018/yahoo-frontend/

(新たにWebフロント技術室という部署が出来上がって、その一環で調査をしたものを記事にしたっぽいです。)

## ヤフー株式会社について
カンパニー制度性

検索: ヤフー組織図

- メディアカンパニー
	- トップページとか
- コマースカンパニー
	- ショッピングとか
- CTO
	- システム統括本部

## 数字
- 従業員数: 6618人
- エンジニア: 2600人
- サービス数: 100サービス

## どんなサービスにフロントエンドエンジニアリングしてる？

広告入稿管理画面のフロントエンド  
Yahoo ディスプレイネットワーク (YDN)  

- フロントエンドの開発チー布人数: 訳１２人
- 開発している年数: 10年
- 2年前: jQuety PHP
- 今: React + TypeScript * Redux + node.js

刷新をしながらもビジネス要件の機能開発を進めなければならない  
並行して3〜4個の機能開発が進んでいく  
コードレビューの時間が爆増  

## フロントエンドエンジニア人数
刷新: 3〜10人  
機能開発: 3〜4人  

## 取り組んだこと
規約の導入  
LintやPrettier  
ツールはGitBookを使う  

### Danger
PRを出すときに行うことを自動化  
レビューメンバーの自動アサインやラベルヒモ付など多数のことをできる  

## TypeScriptの導入
静的型付けによりコンパイル時にエラーが出る  
絹修正時に漏れがなくバグを事前に防げている  

## Atomic Designの導入
コンポーネントの粒度を揃える  
・Atoms molecules Organismsという共通言語を作る  

## コンポーネントガイドの導入

## Redux層の分割
ファイル構成にre-ducksを採用


## 日々素振りを続けて課題に挑む
他にも課題はある、この先まだ道な課題も出てくる

## コマースカンパニーの取り組み
YahooShopping ABテストを回しまくっている  
検索ページの刷新中  
 

## Atomic Designってデザイナーには難しくない！？という話
https://qiita.com/rhirayamaaan/items/7f990e146ec01f2e7e08

qiita: rhirayamaaan


## ABテスト現状
企画: 1週間  
制作: 1週間  
開発: 2週間  
それをミルフィーユ状に  

## UIパーツ集の作成
UIパーツを抽出し共通化

## UIパーツ
社内限定(npm限定)  

ABテストは逆にnpmのパーツを使わなければよいだけ。  
エンジニアも気軽にABテストのデザインが作れる(パーツを利用するだけなので)  

## パーツの社内npmでの管理
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">パーツの社内限定 npmパッケージ化いいな〜<br>   <a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a> <a href="https://twitter.com/hashtag/devsumiB?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiB</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095935180374663168?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## デザイナーはデザイン・リサーチに時間をかけられる
簡単なものならモックがいらない  
(パーツ利用で)数字によって証明された質の高いデザインばかりになる(はず)  

## Webデザイン開発室
サービスの区切りを縦の組織とする  
その縦の組織に特化したほうが成長も速いし効率も良い  
もちろん会社には必要  

が、  
個別最適化されてしまう  

### リソースが無いところはモダン化されていない
- 人材流動ができない
- ナレッジが会社に残らない
- YahooのWebフロントエンドが見えなくなる


## Webフロント技術室
### Webフロントエンドに強い集団
CTOの直下にあるので距離が近い

### 半年間何をやったか
- よく使われているライブラリの効率化  
- 統一したパフォーマンスの計測方法の検討  
- 健康状態の把握  
- 技術選定  


### 健康状態の把握
全サービスのフロントエンドの環境を入力してもらう  
  
エンジニア・デザイナー両方書く

### 方針
**TypeScriptの採用**

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">デザイナーもJS書く前提というのが驚き<br> <a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a>  <a href="https://twitter.com/hashtag/devsumiB?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiB</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095938440544149504?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-conversation="none" data-lang="ja"><p lang="und" dir="ltr"><a href="https://twitter.com/hashtag/devsumi?src=hash&amp;ref_src=twsrc%5Etfw">#devsumi</a> <a href="https://twitter.com/hashtag/devsumiB?src=hash&amp;ref_src=twsrc%5Etfw">#devsumiB</a> <a href="https://t.co/GYylFOv4dY">pic.twitter.com/GYylFOv4dY</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095938822951514112?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-conversation="none" data-lang="ja"><p lang="ja" dir="ltr">CSS周り版 <a href="https://t.co/6qmzCcMXQ0">pic.twitter.com/6qmzCcMXQ0</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095939086466969601?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">この前のスライドで、TypeScriptめ進めていきます的な宣言があったりした <a href="https://t.co/RDdFfVOyDf">pic.twitter.com/RDdFfVOyDf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1095939840053366785?ref_src=twsrc%5Etfw">2019年2月14日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>



## まとめ
TypeScriptとKubernetesやりてえ…という想いが密かに熱くなっています。  
TypeScriptは少しAngularやったときに触ったけど、Kubernetesはどうしたもんか…やはりインスタ映えクラスタか…？🤔  
次個人でJS触るときは絶対にTypeScriptにしよう!  

イベントの感想としては、大手企業がこんなに一同に集まるイベントなかなかないのでは？と思ったのと、それに伴っていろいろとリッチだなと感じました(無料で参加しているのに会場(雅叙園)とか、お弁当(今半すきやき弁当)とか・・・！)  
自分としても興味のある企業がたくさんあったので興味のある内容が多かったですし、刺激もたくさん受けましたのでまた来年も来たいなと思いました。  

