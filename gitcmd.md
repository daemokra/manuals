<!-- TOC -->

- [1. 変更を取り消したい](#1-変更を取り消したい)
- [URLを変えたい](#urlを変えたい)

<!-- /TOC -->

# 1. 変更を取り消したい
- `git checkout <filename>`
\<filename\>を取り消す

- `git checkout .`
特定のファイルではなく、全て元に戻したい場合

# URLを変えたい
HTTP接続でクローンしてたものをSSHに変えたいときなど
リポジトリ変えたときなど

- `git remote -v`
今設定されてるURL確認
- `git remote set-url origin {new url}`
new urlに入れて変更

