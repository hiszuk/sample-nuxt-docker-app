# sample-nuxt-docker-app

## 概要

社内でのWEBアプリ開発入門の勉強会用に作成。

Nuxt.js + Element-UI + Spring Boot + MySQL を docker-compose で一括して起動できるようにしたサンプル。

![実行イメージ](https://hiszuk.github.io/webapp/images/ch12-04.png)

## 起動方法

```bash
# git cloneする
git clone https://github.com/hiszuk/sample-nuxt-docker-app.git my-app

# my-appに移動
cd my-app

# .envのREST_SERVのIPアドレスを実行環境に合わせてvimなどのエディタで修正
# localhostではなく、ipconfigで取得できるアドレスにすること

# docker-compose はインストール済みの前提で
docker-compose up -d

# 上記によりイメージ作成〜コンテナ起動まで実行されプロンプトが戻ってくる
docker-compose logs -f

# MySQL起動が完了していないはずなので、ログを眺めながら気長に待ちます
# M1 MacbookAirで2分くらいかかります
```

# M1 Macの場合

2020年12月30日時点では、MySQLのコンテナに関して特別なバージョンの指定が必要です。

`db/Dockerfile` の1行目をコメントアウトして、3行目のコメントを戻してください

```Dockerfile
# FROM mysql:5.7
# M1 Macな人は、暫定的に下の行を有効にしてください(2020-12-30現在)
FROM mysql@sha256:dce31fcdd15aaedb5591aa89f19ec37cb79981af46511781fa41287d88ed0abd
```

