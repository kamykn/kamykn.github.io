---
title: "Vimconf_2018"
date: 2018-11-24T09:54:57+09:00
categories:
tags:
- event
- VimConf
keywords:
thumbnailImage: /images/post/2018-11-24/01.jpg
thumbnailImagePosition: left
---

今年も行きました！VimConf！
去年も参加した身ですが、今年はなんと言ってもVimの父であるBramが来るということで、EarlyBirdチケットとって参加してきました！

<!--more-->

![VimConf2018](/images/post/2018-11-24/01.jpg "VimConf2018")

のっけから名札の画像に頭を悩ませつつも、来年は予めJPEGで用意するなどの改善をしたいと思いました😇  
(多分PNG-8で保存したのがいけないんや…)

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">わろた <a href="https://t.co/NfFTH5p4vO">pic.twitter.com/NfFTH5p4vO</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066129176388747265?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

↓↓ノベルティの様子
<blockquote class="twitter-tweet" data-lang="ja"><p lang="und" dir="ltr"><a href="https://twitter.com/hashtag/saketoba?src=hash&amp;ref_src=twsrc%5Etfw">#saketoba</a> <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a> <a href="https://t.co/XCTlmp1k7A">pic.twitter.com/XCTlmp1k7A</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066130359610368000?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

VimConfは1日中やっていたこともあり、かなり内容が膨大なので私は下記の内容で今回は書き残します。

- Keynote - What is the next feature?
- Keynote - Vim: From hjkl to a platform for plugins
- その他個人的に思うハイライト
- 懇親会

## Keynote - What is the next feature?
speaker: Yasuhiro Matsumoto (a.k.a. mattn)
Captain of vim-jp
<!--
Skills: Vim, Go, C/C++, C#, Java, Perl etc...
-->

<!--
## agenda
Why we started vim-jp
What is vim-jp
Who knew the next Future of Vim
-->

(この発表で個人的に良いと思ったVim-jpに関してをメインにまとめました。)

### Mattn history
初めてのpatchは5.6.004で当時すでに、日本語の正規表現部分を作ってる人([KoRoNさん](https://twitter.com/kaoriya))がすでにいたそうです。  
ここの部分で日本語の後読みは後ろから探さないから少し遅いなんてことをおっしゃってました。なるほど🤔  
ちなみにVimのドキュメントに後読み先読みのパフォーマンスへの言及が多くてとても参考になりますm(_ _)m。  
(https://vim-jp.org/vimdoc-ja/pattern.html)

### Vim-jpの目的

- 知識の共有
- コミュニティのイベントをココから始めたらいい

というのをやりたかった。  

### vim-jpでやってること
- 英語の壁のサポート
	- マルチバイトとかなかなか気づいてもらえない
	- バグ報告をVim-jpに日本語でしていただければ
	- patch代わりに書いたりしますし、そのままあなたが書いても良い
	- code review
		- patchの内容でなにを直したいのかをVim-jpで吸い上げてレビュー
		- vim本体にintroduceしている

- ドキュメントの翻訳
	- 個人で勝手に書いてもいいけど、間違ったまま広まることも有る
	- Vim-jpが正しく翻訳して品質を保証する

- 機能の追加
	- 追加してきたもの
		- lambda
		- job/channel (NeoVimからの逆輸入)
		- DirectX rendering
			- patchがマージされるまで時間がかかると思ってたら3時間でマージされた
		- incsearch
		- :terminal

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">『ドキュメントの翻訳は個人で勝手に書いてもいいけど、間違ったまま誰も指摘せず広まることも有る』 確かに🤔  <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066141610495234048?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### 誰がVimの次の機能を作るのか
Vim-jpは開発者集団だけど、Vim-jpが作っているわけではない。  
(patch投げるときにサポートなどもしてるのでVim-jp以外の日本人も作っているという意味)  
そういう意味で、次にどんな機能が入るかはVim-jpではなんとも言えない。  
ただし、開発者集団なので、Vim-jpのメンバーも作ってpatch投げるよ！  

### Suggestion (パッチ書いたよ、採用されるかはわからないけどね)
というわけで、mattnからの機能の提案

- DRCS Sixel on :terminal
- ch_listen()
- BLOB type

<!--
## 質問
### 苦労したpatch
- Vimのsyntax highlightが突然消える件
	- タイムアウトで真っ白けになる

### Vimのデバッグ方法
- debug vim
	- ステップ実行できる

## atWare [スポンサートーク]
speaker: guyonさん
- Yokohama.vim 8年
- vimconf 2015年 speaker

- SIer
- Java/Scala

- atWare入社時の面接
	- アジャイルしたくてという動機
	- 面接ではVimの話を大半した
		- 転職できた
- atWare入社後
	- 社内でVim浸透活動を定期的にした
	- 昨年VimConfのスポンサーになれた
	- 「アットウェア v」でサジェストで「アットウェア vim」と出る
	- スポンサーになる稟議を出した
		- 昨年と同様  ... いや、同様でいいのか???
			- 最大限できることはなにか
			- 結果今回のような形に

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">atWareさんのVimに対する想い <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066152306427613184?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

-->
## Keynote - Vim: From hjkl to a platform for plugins
speaker: Bram

この発表ではVimの歴史を最近Bramが思っているプラットフォームとしてのVimという側面から振り返ってみる内容になっていました。

### 最近出版された本
- 最初は(昔)はVimの使い方だった
- 最近、どうやってプラグインを入れるかなどの本が出た
- プラットフォームとしてのVimの側面

### 最初のViの機能
#### できたこと
- .exrcファイル
- Undo 一回分
- .swp メモリが少なかったので必要だった
- recursive map マッピング
- Jump around with mark

Viで要求されなかったので、できないことは沢山あった。(たくさんのメモリを要求するので求められなかった)

### Vim History
#### Autocommands
**Added in Vim 4.0**  
ユーザーの任意の処理を狙ったタイミングで実行可能にするHooksの提供  
例) `:au BufRead `

Autocommand(BufRead、BufWrite)がbufferに対して何でもできる問題が発生
- 解決できる方法の模索
	- BufWrite時にbufferの中身を消すなどはできないようになど

#### Vim script
**Vim 5.0から**  
Vim scriptは`syntax highlight`などでまず使われた。  
と同時に.vimrcをコピーしなければいけない問題が発生。  

#### plugin
**Vim 6.0**  
正しいディレクトリにpluginを置けば動くように。  
'runtimepath' optionの提供。  

いくつかの機能がプラグインで提供されている。

##### Data types added 
Pythonから影響を受けている

- Number
- Float
- String
- List
- Dict
- Funcref, pertial
- special
- job
- channel

(BLOBはいつ来るかわからないけどその正当性を考えてみたいとのこと)

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">Bram「エディターにFloatは要るのかと思ったが、要ると言う人がたくさんいた」<br>😆 <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066157002676551680?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### plugin performance
`profile`: performance を 測りたいときにおすすめ

あと、`vim --startuptime`

### プラグイン高速化
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">Bram氏 『プラグインをどう高速化するか？<br>- Loading time<br>- Execution time<br><br>→ 高速なコンピュータを買えば解決！！！』😆 <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066158383600824320?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
なんだけれども、では実際に改善をする場合には？という内容が続く

#### Autoload
などをまずは使って適宜ロードするようにするとLoading timeは改善される。

### Vimの改善による高速化案
### 1. Improve parsing speed
- Multi-threadingで動かす
	- 別のthreadで動かせばメインのスレッドには影響がない

別のネームスペースで動かして他のスレッドに影響しないようにしなければならない  
→ いつの日かできるといいね

#### 2. Vim script以外の別の言語が使える
- Python
- Perl
- Ruby, Tcl, Scheme
- Lua

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">『プラグインのスピード改善のために、他の言語を実行可能なようにサポートしてきたが、それは正しいhelpだったか？ それならば私達はVim scriptを早くしたほうが良い。』 <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066160254113599488?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Vim script コンパイル案が WIPらしい
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">自分が昨日お披露目したspelunker.vimもVim script 100%なので恩恵受けられたらいいな〜 <a href="https://t.co/DhxpR9YhGZ">https://t.co/DhxpR9YhGZ</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066161352517967872?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


### Plugin management
plugin dependencies  
plugin は パーツとしてライブラリのように扱われることもあるので  
それらを依存管理させたい？  

### 実施案
dependencies.vim ファイルに依存を宣言させる  
例)  
```
let g:mypluginvimproc = PluginDepend('github', 'Shougo/viproc.vim')
```

自分のプラグインでは
```
call PluginLoad("~~~")
```

V2やV3などの別名をつけることで、共通でなるべく使うようにしたい。

<!--
### plugin test
assert_function()
feedkeys()
screenshot test
-->

### 欲しい機能について投票を開催してみた

- 193票: popup window to show hints/message and pick an item
- 179票: Store propertise with text, used for highlighting et al.
- 96票: vim script 高速化

#### text properties
どういうアプローチか→  

```
function    foobar (hogeohge)
└statement  └name   └some properties
```
というようにプロパティをつけていく。ハイライトなどに適応できる(非同期でできたらいい)  

やるにはかなりの機能が必要  
Vimはlineを扱っていたけど、fileとして扱わなければいけない  
(fileはGBのものもある)

#### popup window
このメッセージをこのポジションで見せたい  
text propertiesと似たようなアプローチでできそう  

### 質問
- 投票の中で大好きな機能は
	- text properties

- LSPについてどう思う
	- Bram: ごめん聞いたことがない
	- LSPはプラグインでサポートすべきなのか、本体でサポートすべきなのか教えてくれ！

### Bramの発表について個人的なまとめ
今回の発表から、Plugin PlatformとしてのVimという立場を認識させられました。  
つまり、『みんなプラグイン』を作れというメッセージとして受け取って良いのかな？


<!--
# Migrating plugins to standard features
プラグインを標準機能で置き換える
Vim has many useful features built-in

- プラグインに依存していたけどVimの標準機能でもできそう

- Testing Engineer meet Vim
	- デバイスのログを見るために使い始めた

- Vimを使う時間を増やすためにtest programmer から programmerに

たくさんのVimに依存している状態を脱したい
- spartan vimの影響

- NeoComplete
	- たくさんVimにはデフォルトの補完がある
	- 行補完だと golangの `if err != nil {` を一発で保管できる
		- 続けて `return err` と `}` も保管できる

- NeoBundle
	- Shellスクリプトで書くのもいいけど、Vimスクリプトで書くとWin/Linuxの違いを吸収してくれる

- Unite
	- 今回は主にFiler
	- MRU, under current or buffer path, Loaded plugin

	- Filer
		- 作った

自分の必要な範囲を把握してミニマムにまとめる

https://twitter.com/dice_zu/status/1066190854795091968

# Modes
Tatsuhiro Ujihisa
- Vimのモードの切替のはなし
	- vimtutorをやるといいよ
	- :h
	- 7 modes + 7additional mode
	- :help mode-switching

- Ujihisa
来年はバンクーバーに戻る
2年くらい前までカナダのバンクーバーにいた

## GDB
- the GNU Project Debugger
	- GDBを使うにはMakefileを変えてbuildする
- Termdebug
	- powered by :terminal
	- Vim用のGDBのラッパーplugin

https://twitter.com/ujm/status/1066209109668651009

# A day in the life of (ordinary) Vimmer
- OKURA Masafumi
	- 普通のVimユーザーの1日

## ユースケース
- 日々の開発
- コードレビュー
- remoteサーバーのファイルを編集/見る

## Why not modern editors
AtomはVimPluginは使えない

## Why not IDEs
特にRubyMine
Open sourceではない

## 朝
Vim / NeoVimの更新
Pluginのこうしん
cow's quoting

## plugin
- deoplete, UltiSnips
- ale
- vim-test
- fugitive
- gitgutter
- fzf


# Modern editor-independent development environment for PHP
tadsan
UsamiKenta

Emacsの人

## 宗教戦争
- code of conduct
- 他のエディタ動向を探っているはずなので紳士的に他のエディタに対して接するべき

## PHP
Rasmus
PHP最初に作った人
- PHPにはいろんな機能があるよ

Pixivでも手続き型からOOPに書き換わっていた。

過去の開発スタイル
IDEなどなかった
Ecripseのような重いエディタでも大して静的解析してくれない

## Phan ,PHPStan, PHpactor
静的解析する方法

## Veonim
vim IDE

https://twitter.com/tadsan/status/1066213079669559296

# Effective Modern Vim scripting
Alisue

Create your own
Vital.vim

非同期処理でPlugin作り直したくなってきた

# Vim ported to WebAssembly
EmscriptenはC/C++をwasmに変換する
CでVimが書いてあるのでVimもwasmにコンパイルしたくなる。

emconfigureがconfigureのラッパースクリプト

what is hard

Debbugging is hard
- ステップ実行できない7.0まで
- chrome 7.1からできるらしい

Can't sleep
emscripten_sleep()
EmterPrinter

Impressions
tiny featureを便利に感じたことはなかったけど，これのおかげで便利に感じた

質問
emacsからwebkit開いてwasm実行できてvim動かしたい
リサイズができない？

自作プラグインのWeb上のサンプルとして使えないか


# LT
## Vim-orgmode
Takaaki ISHIKAWA

org-mode

## Nvimからブラウザを操作したい
notomo

ブラウザ terminal間の移動辛い…

Nvimからブラウザを操作するプラグイン
ctrlb.nvim

Golang Typescript
WebSocket

Nvimでfizzbuzz


## VimPhone 2018


## Vim8 の Neovim違い

## vim-history
K.Takata

Git上では7.0しか見れないけど、1.14から見れるようにしたよ

githubのvim-historyは vim 7.0 (2004) から
1.14 ~ 5.4 commit manually

Vimのpatch数ベスト3
Brabandt
takata
mattn

-->

## その他個人的に思うハイライト
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">atWareさんのVimに対する想い <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066152306427613184?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
今年のPlatinum SponsorのatWareさん

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">面接でVimのことを話して転職成功した例が、今日2件確認された <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066183439395647488?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
2件 = atWareのguyonさんとdaisuzuさん

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">翻訳 「cのなかになにがあるかみたいシー」<br>素晴らしいww  <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066195687249833984?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
ujihisaさんの発表の中の「cの中をseeしたい」の同時通訳。

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">vim.wasmの力でWeb上でプラグインのサンプルすごくいい <a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066235303369666561?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
質問された方の内容もめっちゃ良かった


## 懇親会
懇親会ではいろいろな方とお話させていただきました。

中でも個人的に記憶に残っているのは…

### Bramと写真撮った
写真はここには載せませんが、スゴイいい思い出になりました😆  
私は英語がそんなに話せないですが、VimConfにようこそ！！って握手してくれました。
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">酔った勢いに任せてVimの作者のBramと写真撮ってもらって握手してもらったので非常に満足😊<a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066283714957651969?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### 韓国人の方と話した
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">懇親会でたまたま日本語喋れる韓国人の方と一緒に話したのでmattnさんは知ってた？って話したら「mattnは世界的に有名です」って言ってた😆<a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1066287997547503616?ref_src=twsrc%5Etfw">2018年11月24日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

こちらも韓国人の有名なプログラマーといえば個人的にはFZFの作者の[junegunn](https://github.com/junegunn)さんですなぁというお話をしたのと、チャットアプリは日本で人気なのはLINEだけど韓国はKakaoTalkでしたっけ？みたいな話をしました。(その方はNAVER時代の子会社で働いていた事があるらしい。)  
Bramとの写真は流れでこの韓国人の方と撮ったので、LINEで写真送りつけましたww(通常韓国の方はLINEはスマホに入れないけれども、NAVER関係でたまたま入れていたとのことww)

### ほかにも
- いろいろとTwitterでよく見るアイコンの方と少しお話できてよかったです😆
- (直接はお話できませんでしたが) LTやってらっしゃったのでb4b4r07さんを初めて目撃した
	- (zplugお世話になってます！)


## それではまた来年
VimConfは個人的にもVimについて振り返るよいタイミングではありました。  
今年自分、Vim活したっけ？あれ、去年のVimConf以降なにもしてない…ヤバイ。  
みたいな一つの自分を奮い立たせるための口実にしていたりします。  
そんなこんなで作ったのがspelunker.vimです。  
https://github.com/kamykn/spelunker.vim  
  
VimConfは自分のモチベーションの源です。  
来年もVimConf楽しみにしています😆




