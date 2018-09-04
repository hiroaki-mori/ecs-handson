step0:Dockerに触れてみる
====

#Docker Hubからローカルへイメージを保存

```
# ubuntuの公式イメージを保存
docker pull ubuntu
```

#ローカルで保持しているイメージ一覧
`docker images`

#コンテナを起動

```
# イメージ:ubuntuよりコンテナ起動
docker run -it ubuntu
```

#コンテナを停止
上記で起動した場合、exitすると同時に停止される
`docker stop`
#コンテナの一覧取得
IDや起動状況等が確認できる
`docker ps -a`
#コンテナの破棄
`docker rm test {CONTAINER ID}`

#イメージの登録

```
#起動
docker run -it ubuntu
#コンテナ内でファイル作成
echo "Hello, World!" > test.txt
ls
exit
#コンテナから新規イメージ登録
docker commit {IMAGE ID} test-ubuntu:latest
#新規イメージからコンテナ起動
docker run -it test-ubuntu
#コンテナ内でファイル確認
cat test.txt
```

# 次へ

`git checkout -b local-docker origin/local-docker`
