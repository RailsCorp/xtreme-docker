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

### 3. 必要なものをインストール

```
$ brew install unison
$ gem install docker-sync
```

### 4. ホスト、ローカル感を同期

```
$ docker-sync start
```


### 注) なんか困った時のコマンド！
```
$ docker-compose up --build
```


コンテナが起動してるかのプロセスの確認
```
$ docker ps
```


あったら`ok`