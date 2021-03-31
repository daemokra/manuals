# 特定のコンテナの端末に入る
`docker exec -it <コンテナ名> bash`

docker exec -it とは
-iは、Keep STDIN open even if not attached
標準入力を開き続ける。

-tは、Allocate a pseudo-TTY
疑似ttyを割りあてる。


# コンテナ一覧表示
`docker ps`

