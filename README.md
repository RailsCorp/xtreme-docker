# xtreme-docker

今まで、vagant で開発してきましたが、
今回を機に、dockerに移行しようと思い始めました。

環境を整えたので、以下の手順を実行してください

### 0. docker for macをインストール

## Dockerコマンド実行

### 1. まずは、clone(このxtreme-dockerはcloneしてある前提)

```
git clone https://github.com/RailsCorp/xtreme.git
```

`xtreme-dcoker`配下で以下のコマンドを実行.(必ず、docker-compose.yml)がある場所で実行すること！


### 2. xtreme/Dockerfileに基づいてimageを生成し、そこからコンテナを生成する。

```
$ docker-compose up
```


バックグラウンドで実行したかったら
```
$ docker-compose up -d
```

このコマンドで`rails s `が含まれているので、もうする必要はない.

うまくいけば、`localhost:20000`がうまく起動されるはず！

### 3. 必要なものをインストール

```
$ brew install unison
$ gem install docker-sync
```

### 4. ホスト、ローカル間を同期

```
$ docker-sync start
```


### 注) なんか困った時のコマンド！

- mysql.sockがない遠これらた時、
https://qiita.com/musaprg/items/572489a829a7d3b9830d

- まぁ、あんまり変更する必要ないけど、もしdockerfileとかを変更したら、、、

```
$ docker-compose up --build
```

- コンテナが起動してるかのプロセスの確認
```
$ docker ps
```
`xtreme-docker_webapp`と`mysql:5.7`があれば問題ない

- dockerのコンテナ内に入る時、

xtreme-docker_webappというコンテナ内にbashを使って入る。
```
$ docker exec -it xtreme-docker_webapp bash
```

### sequel proの設定

```
名前: localhost
ホスト: 127.0.0.1
ユーザ名: root
パスワード: root
ポート: 13306
```

これでログインできる。