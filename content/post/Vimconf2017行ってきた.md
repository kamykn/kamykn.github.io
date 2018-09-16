---
title: "Vimconf2017行ってきた"
date: 2017-11-04T23:56:49+09:00
draft: false
tags:
- Vim
- VimConf
thumbnailImagePosition: left
thumbnailImage: /images/post/20171105000423.jpg
<!-- coverImage: /images/post/20171105000423.jpg -->
<!-- metaAlignment: center -->
<!-- coverMeta: out -->
---


※この記事は旧ブログから当ブログに記事を移行しました。

<!--more-->

![VimConf2017](/images/post/20171105000423.jpg "VimConf2017")

# Vimconf2017行きました！


場所は秋葉原の富士ソフトビル5F。
VimConfのTシャツ貰った！
あと、コーヒーの紙コップがVimConf仕様になってたり、お弁当が今半だったりといろいろとすごかった。

そして何よりも、最初に受付で会話したのがkaoriyaさんだったという事実を理解するのに時間がかかった。

~~参加申し込みが遅くなって~~普段使わせていただいているVimにお世話になっているので、コミュニティへのお礼も兼ねて個人スポンサーで参加しました!



# 内容について
[VimConf2017公式](http://vimconf.vim-jp.org/2017/)

にもありますが、予定通り、

- Vim, Me and Community (haya14busa)
- The Past and Future of Vim-go (fatih)
- Talk show (mattn, k_takata, kaoriya)
- Creating your lovely color scheme (cocopon)
- vim-mode-plus: The most ambitious vim emulator in the world (t9md)
- Vim and Compatibility (senopen)
- neosnippet.vim + deoppet.nvim (ShougoMatsu)
- How ordinary Vim user contributed to Vim (dice_zu)
- The new syntax highlighter for Vim (p_ck_)
- You've been Super Viman. After this talk, you could say you are Super Viman 2 -- Life with gina.vim (lambdalisue)
- After-Party

となっておりました。

## Vim, Me and Community (haya14busa)
haya14busaさんは若いのに素晴らしいの一言で、今年の4月からはGoogleで働き始めたそうです。  
incsearchはVim本体に取り込まれたということもあり、最初はプラグインの修正から入り、Vim本体の貢献までの経緯がわかるような内容でした。

## The Past and Future of Vim-go (fatih)
Vim-goの作者fatihによる発表。  
Vim-goは、方向性や決まりをしっかり作って開発に参加しやすい環境を作るのに集中したとのこと。  
ほかにも『寄付は自分の時間を使って貢献しているのだから、躊躇うことはない』という話など。

## Talk show (mattn, k_takata, kaoriya)
最近追加された機能、個人的に印象深いパッチ、Vim-JPについてなど、語られてましたね。  
これは来た人が楽しめるようなものだと思うので、特にノーコメントで…！

## Creating your lovely color scheme (cocopon)
自分のカラースキームの作り方についてまとめられていました。  
この発表の後から他の発表者のコンソール画面のカラースキームが気になりすぎてやばい。

## vim-mode-plus: The most ambitious vim emulator in the world (t9md)
Vimのコマンド体型をatomに実装するのと、さらに便利な機能を追加したというお話。  
Vimに逆輸入してくれとかいう話をAfterPartyで話してたら、もうできてた。何を言ってるのか わからねーと思うが(略)

https://github.com/haya14busa/vim-edgemotion

## Vim and Compatibility (senopen)
POSIX原理主義者怖い。  
とはいえ、どこでも通用する.vimrcを考えるとPOSIXは考慮すべきですよね。

## neosnippet.vim + deoppet.nvim (ShougoMatsu)
snippetの実装手段と仕組みがよくわかりました。
最初のDark Powered プラグインのリストでdeopleteがvim8対応って表記がわざわざ避けられててアレって思ってたら、ここ一週間に対応したよって話が最後にあった。

## How ordinary Vim user contributed to Vim (dice_zu)
めっちゃOSS貢献しているわけではないけど、それでもVimのコントリビューターにはなれるよというお話。
毎日Vimのビルドすると良い。まじで。

## The new syntax highlighter for Vim (p_ck_)
自分でhighlight作ったよというお話。
matchaddpos()でやってるって話を聞いた瞬間重そうと思ったけど( CCSpellCheck.vim https://qiita.com/kmszk/items/ce536aff00f44960e811 の経験から)、やっぱり1万行レベルだと重たいみたい。
つまるところ正規表現の方が早いという解釈とも取れるけど、いいのかな…？

## You've been Super Viman. After this talk, you could say you are Super Viman 2 -- Life with gina.vim (lambdalisue)
gitをVimから操作するためのプラグイン。
fujitive.vimよりも使いやすそう、乗り換えるべきか…

## AfterParty
LT大会があったり、みんな使っている言語や環境の違いからそれぞれのVimの使い方してて、自分も『何かしてみたい感』が高まった(何かするとは言ってない)。  

とりあえず、お昼にVimでメモ取ってるときにCCSpellCheck.vimのバグっぽい挙動を見つけたから、それ直したら次に何したいか決めるか…。

## また来年
初めてVimconfに参加したけれども、かなり良い刺激を受けたので、また来年も是非参加させて下さい！(もちろん個人スポンサー枠で…？)



