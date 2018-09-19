---
title: "GoogleCloudNext18 基調講演"
date: 2018-09-19T14:39:49+09:00
tags:
- GoogleCloudNext'18
keywords:
- tech
- GoogleCloudNext'18
---

基調講演で素晴らしいと思ったものをいくつかまとめました  
主に機械学習の利用例多めかもしれません。


<!--more-->

※ あと、参加が30分ほど遅くなったので最初の方は聞いてません。

## Cloud AutoML (※ML = Machine Learning)
- Machine Leaningの自動化
  - AutoML Vision
    - 画像の機械学習
- AutoML Natural Language
  - 自然言語の機械学習
- AutoML Translation
  - 機械学習を使った翻訳プロダクト

## AutoML Translation デモ
### 『ドライバ』: 文脈によって違う
 <blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">例えば『ドライバ / Driver』はPCなのかゴルフなのかドライブなのかで違う</p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1042232477920555009?ref_src=twsrc%5Etfw">2018年9月19日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">それをAutoML Translationで日経が使おうとしていて、記事の世界同時配信をしようとしている。</p>&mdash; かみけん (@_kamykn_) <a href="https://twitter.com/_kamykn_/status/1042233150724685824?ref_src=twsrc%5Etfw">2018年9月19日</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## なぜカスタマイズする必要があるのか
- カスタマイズモデルのほうが翻訳の精度高い
  - その文脈にあったモデルを使っていくことで精度が高くなる
- 主要業界に特化したAIを用意する
  - 小売
  - 金融
  - とか
  - とか

## GSuite

400万のビジネス(会社で使われている)  
ファーストリテーリングがGSuitsこれから使うと先ほどの発表であった  

### GSuiteのこれから
#### 共同作業に費やす時間をへらす
**Google Calender**  

行動パターンや距離などから適切な会議室の自動提案  

**共同作業**  
ヒトが共同作業に費やす時間は全体の74%  
(メールやビデオチャットファイル共有する行為も含まれる)  

なので、GoogleはGSuitsに力を入れていってビジネスをもっと良くしたい。  

## 変革
- クラウドテクノロジー
- 会社の分化

の理解が必要(無しには出来ない)

## 変革の例
- sansan / eight
    - Hujikura Shigemoto : CTO
    - サービス
   	    - 法人向け名刺 / 個人向け名刺
            - 奇跡的な出会いが日々起こっていて
            - その際に必ず渡す名刺を管理する
   - 経緯
   	    - GCP
            - Cloud Vision API
                - OCR 画像からテキスト化
                - 本番利用中
                - emailアドレスは1文字でも間違っていると送れない
                - 99.9%を実現する為に技術を高めている
           - データの分析も
                - コストダウンとさらなる付加価値
- 丸紅
    - Omnis
        - http://www.marubeni-sys.com/msys_omnis/
    - 活用
        - コールセンターの通話内容のテキスト起こし
        - データ分析への活用
        - 応対記録残すとか手間暇かかる
        - 録音: オンプレ、解析: クラウド
        - 通話内容はセキュリティが高くないと置けない(金融の取引先とか)
        - Googleのおかげで方言も行けるらしい…！？
- PLAID
    - KARTE
        - アプリの利用者の可視化
        - パーソナライズ
        - CXプラットフォームとしてのサービス
        - (誰が今、サイトに来ていて何をしているかを知らずにサービス提供するの？ と言いたそうに感じた)
        - カスタマーサポートにも使える
        - マーケティングに使える
    - 選定の理由
        - 多様性
        - 秒間2〜3万イベント
        - リアルタイム性
        - BigQuery
        - やるべきことにフォーカスできた
        - インフラコスト
            - 1/3のコスト増にとどまっている

