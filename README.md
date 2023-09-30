dockerをインストールする
https://matsuand.github.io/docs.docker.jp.onthefly/desktop/mac/install/ (macの場合)

railsアプリを置きたいディレクトリに移動して
``` 
$ git clone https://github.com/nagmo01/rails-docker.git
```
でローカルにrailsの各種ファイルをコピーする

```
$ docker-compose up -d
```
でrailsのコンテナとpostgreSQLのコンテナを起動する
この後にもまだ操作をしたいため```-d```をつけてバックグラウンドで実行します。 


```
$ docker ps # rails-docker-webという名前の方のコンテナIDをコピーする
$ docker exec -it <貼り付け> bash
```
とするとコンテナの中のシェルを操作できるようになるため、
(root~と出てる)
```
$ rails db:create #database.ymlをもとにデータベースを作成
$ rails db:migrate
```
を実行してから
```
$ exit 
```
で抜ける

ここからまたホスト側に戻る

```URL:localhost:3000```にアクセスしてみる。

エラーなど出ていなければ無事成功。
