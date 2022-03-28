# Dockerでの環境構築

PLATEAU VIEWはAWSを使用して構築されていますが、AWSを使わずに構築することができます。
その一例として、ここではDockerを使用したものをご紹介します。

## 前提

Dockerがインストールされていることを前提としています。

## 手順

### PlateauViewのソースコードのクローン

下記を実行します。

```shell
cd src
git clone <TerriaMapのリポジトリ> TerriaMap
cd TerriaMap
mkdir packages && cd packages
git clone  <TerriaJsのリポジトリ> terriajs
cd ../../../
```

### Dockerイメージのビルド

本プロジェクトのルートディレクトリ(docker-compose.ymlがあるディレクトリ)で、下記を実行します。

```shell
docker compose build
```

### PlateauViewの起動

下記を実行すると、ポート80でPLATEAU VIEWを見ることができます。

```shell
docker compose up -d
docker compose exec terria /app/node_modules/.bin/pm2 start /app/ecosystem-production.config.js --update-env --env production
```

### PlateauViewの停止

下記を実行します。

```shell
docker compose up -d
docker compose exec terria /app/node_modules/.bin/pm2 start /app/ecosystem-production.config.js --update-env --env production
```


