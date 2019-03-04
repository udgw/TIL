# dockerの使い方

## Dockerfileを書く

Dockerfileとは：　コンテナのMakefileのようなもの(雑)

例：alpine linuxの中でgccを使う

```
FROM alpine:3.4
RUN apk --update add gcc && rm -rf /var/cache/apk/*
CMD echo 'hello docker'
```

- CMDはdockerを実行したときに実行されるコマンド


## docker buildコマンドでbuild
- -fオプションでDockerファイルを指定
	- Dockerfileという名前であれば-fで指定しなくて良い)

- -tオプションでイメージ名を指定
	- alpine-gccという名前でイメージをビルド

```
docker build -f Dockerfile -t alpine-gcc .
```

## ビルドしたイメージの確認

```
docker images
```

## コンテナの実行

```
docker run --rm -t -i alpine-gcc /bin/ash
```
alpine-gcc内のashを実行し、docker環境の中に入る
単にDockerfile内のCMDで指定した処理を実行させたい場合は

```
docker run image_name
```

でよろしい。

## 作成されたイメージの一覧

```
docker images
```
で取れる。


## 動いているコンテナの一覧

```
docker ps
```

## 削除
### 動いているものの停止

```
docker rm <image_id>
```

### イメージの削除

```
docker rmi <image_id>
```

## docker-compose
- 複数のコンテナをまとめ上げてビルドしたり走らせたりできる
	- 運用する場合はかなり楽になると思われる

## 永続化等について
何種類か方法がある

- ホストとの共有ボリュームをマウントする
- 専用のコンテナを立ち上げる
	- 詳細不明

- ボリュームのマウントについて



