## dockerコマンド

###docker pull
* イメージを取ってくる
	```
	docker pull ubuntu
	```
* タグを使ってイメージのバージョンを指定
	```
	docker pull ubuntu:12.04
	```
### docker build
* キャッシュ無効
	```
	docker build --no-cache=true
	```
### docker images
* Docker コンテナの一覧を表示する
### コンテナの起動・プロセス
#### docker run
```
docker run [option] image [command]
```
* `-i`と`-t`のオプションをつけるとターミナルでコンテナを実行できる
#### docker ps
```
docker ps [options]
```
#### docker exec
* 起動中のコンテナに追加プロセスを実行
