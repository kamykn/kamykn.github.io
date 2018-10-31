---
title: "vimconf.swp 2018"
date: 2018-10-31T19:38:24+09:00
categories:
tags:
- event
- VimConf
keywords:
thumbnailImagePosition: left
thumbnailImage: /images/post/2018-10-31/1.jpg
---

.vimconf.swp行ってきました〜！  
今回のイベントはVimConf2018のRubyで言うところのRejectKaigiに当たるようなものだそうで、  
VimConfでは惜しくも採択されなかった発表やVimConf準備の舞台の裏話が聞けるかもということで楽しみにしてました😊


<!--more-->

![.vimconf.swp](/images/post/2018-10-31/1.jpg ".vimconf.swp")

自分は仕事もあったので19:20くらいに会場に着きました。  
ちょうど入室したときには、聞き覚えのある声。  
この声はまさか…！  

# Differences between Nvim and Vim full version ([@Shougo](https://twitter.com/shougomatsu)さん)
残念ながら最後の方しか聞けなかったのですが、  
最後のほうでGonvimを紹介されていました。  

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">Gonvim初めて知った😲<a href="https://t.co/tMk0wnyKFZ">https://t.co/tMk0wnyKFZ</a><a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1057579907453075462?ref_src=twsrc%5Etfw">2018年10月31日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

早速、Macに入れてみました。これでこのMacには何種類目のVimが入っているんだろう🤔  
ヘッドレスのneovimのGoでGUIにしているやつみたいです…なるほど！  

ヘッドレスneovimといえば自分は一時期OniVim使ってました。  
GUIがエレクトロンでデフォルトの設定がチョット自分には合わなかったので、できるだけ素のVimに戻していってあげて使ってました💪  
…でも今はまたVim8に戻ってきていますw  
(terminalにやっぱりこもりたかったので)  


# 僕の推しVimプラグインを見て！([@aiya000](https://aiya000.github.io/)さん)
## 見た目系
目についたもののメモです。  
後で調べよう_φ(･_･  

- LeafCage/foldCC
	- foldの最初の数行見える
- andymass/vim-matchup
	- カッコの拡張
	- 対応カッコが画面外にあってもステータスバーに出してくれる
- deris/vim-shot-f
	- fから飛べる場所をハイライトしてくれる
- machakann/vim-highlightedyank
	- yankしたときに該当箇所をチカっとハイライト
		- そもそも素だとyankできたかわからない
			- → わかりみ

## 編集編
- cohama/lexima.vim
	- 対応カッコとか勝手に入れてくれる
		- (個人的にはコピペで暴れたので外したりした…)
- rhysd/vim-operator-surround
	- カッコ関連の入力の補助
- thinca/vim-textobj-between
	- ある文字とある文字の間
	- *とか_とか…！
- Chiel92/vim-autoformat
	- コードフォーマット
- aiya000/vim-fmap
	- fsuで『す』に飛ぶ

# Elegant collaboration of Vim and Ruby ([@pocke](https://twitter.com/p_ck_)さん)
- ゴール
	- vim scriptじゃなくてrubyでけるようになる

## ruby in your .vimrc
Rubyを.vimrcで書くには

```
ruby << EOC
  rubyの記述
EOC
```

## Vim plugin with Ruby
- rubyeval()をVimscriptに足したい
	- 数値や文字列はできたけどハッシュとかめんどくさくなってきた

## More rich library for Ruby
野望: Rubyからvimコマンド呼び出したい

たしかに、好きな言語でプラグイン書きたいしVimコマンド呼べたらいいなと思いました😆

# Vimのhelpbotは裏で何をしているのか ([@thinca](https://twitter.com/thinca)さん)
- :helpしてますか？
	- 実はめっちゃ充実してるよ

- helpbot
	- vimのhelpを返すbot
	- 実は裏でvimが起動している
	- バッチモード
		- 標準入力にVimScriptを流し込む

- スーパーVim芸の説明タイム
	- rangeは結構便利にできているとのこと

shell芸ならぬVim芸😆

# iOS Dev Workflow with Vim (jkaplanさん)
- swiftと開発環境
	- xcodeに依存している
		- オープンソースになったけどチョット足りない

- why vim
	- 他の言語でも使える
	- キーバインドが指に優しい
	- 軽い
	- プログラマブル

- XVim2
	- key-bindings for Xcode 9らしい
		- 不安定
		- xcodeの証明書無効にしなきゃいけない(!)
		- ということも有り業務では使えない

- Neovim で使っているプラグイン
	- Deoplete
	- Ale
	- vim-gutentags
	- vim-tmux-navigator
	- FZF

- 複数ファイルの置き換えはやっぱりxcodeのほうが正規表現など気軽に使える

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">(自分もfzfはVimもzshのときでも依存しまくってる😆)<a href="https://twitter.com/hashtag/vimconf?src=hash&amp;ref_src=twsrc%5Etfw">#vimconf</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1057593395365916674?ref_src=twsrc%5Etfw">2018年10月31日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


# Vimconf2018について

- Bramがくる！
- 6時間半の充実した1日になる
- スポンサーが今年は非常に多い
- 今年のCFPは締め切ったが、来年応募するといいことあるかも…！


# まとめ
VimConf2018がさらに楽しみになってきました！😆  
あと、会場がIIJさんで実は個人的に(というか夫婦で)mioにはお世話になっています。  
素晴らしい会場でした。  

![.vimconf.swp](/images/post/2018-10-31/3.jpg ".vimconf.swp")

![.vimconf.swp](/images/post/2018-10-31/2.jpg ".vimconf.swp")

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">vimconf.swp楽しかった！<br>最初に話した2人が学生でビックリだった😆<a href="https://twitter.com/hashtag/vimconfswp?src=hash&amp;ref_src=twsrc%5Etfw">#vimconfswp</a></p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1057618038638276609?ref_src=twsrc%5Etfw">2018年10月31日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
(↑@懇親会)

それでは今度はVimConf2018でまたお会いしましょう〜。  

