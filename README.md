# はじめに
サクッとredmine環境をdocker上に構築する手順です。
冗長化は考慮されていないので、DBのバックアップはしっかりとったほうがいいかもしれません。

# dockerのビルド
git pull …
docker-compose.ymlを編集。
<>で囲まれているあたりにお好みの設定を入れてください。

docker-compose build

# DBの構築
いきなりdocker-compose up -dをすると、DBができる前にAPが起動して落ちるので、一つずつ丁寧に構築する。

docker-compose up db
※mysqlの処理が終わったらCtrl+Cで止める。

# DBを通常起動する
docker-compose up -d db

# AP(redmine)の構築
docker-compose up app
※Railsのmigrateが終わったらCtrl+Cで止める。

# APを通常起動する
docker-compose up -d app

# redmineにログインする

http://localhost:8080

※docker-compose.ymlでappのportを変更している場合は、適宜読み替えてください。

以下のパラメータでログインできます。

|parameter|value|
|---------|-----|
|id       |admin|
|password |admin|

※ログイン直後にパスワードの変更が必要です。
