# 環境構築
## Macの環境構築
```
brew install hugo
ghq get git@github.com:kamykn/kamykn.github.io.git
```

# 使い方メモ

```
# 確認
hugo server

# ビルド
hugo

# 記事作成
hugo new post/<記事名>.md

# push
git push origin HEAD # いつもの
git subtree push --prefix public origin master # subtree の push

# submodule更新 (これ忘れるとhugoコマンドで静的ファイルが作られない)
git submodule update
```

# 構築時のメモ
README.mdをmasterに追加しないと表示されないので注意。

