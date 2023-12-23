# robosys2023 ros2 talker listener

ロボットシステム学　課題2提出用リポジトリ

[![test](https://github.com/yodaishiota/robosys2023_mypkg/actions/workflows/test.yml/badge.svg)](https://github.com/yodaishiota/robosys2023_mypkg/actions/workflows/test.yml)

## 機能について
パブリッシャーのtalkerとサブスクライバーのlistener間の通信の様子を確認する

## 事前準備
ros2がインストールされていなければ最初にros2のインストールを行ってください。
以下のコードを実行し、ワークスペースを作成して本レポジトリをクローンしてください。
```
$ mkdir -p ros2_ws/src
$ cd ros2_ws/src
$ git clone https://github.com/yodaishiota/robosys2023_mypkg.git
$ cd ~/ros2_ws
$ colcon build
$ source ~/.bashrc
```
さらに以下のコードを実行することで、事前準備は完了します。
```
$ cd ~/ros2_ws
$ colcon build
$ source ~/.bashrc
```

## 使用方法
talkerを立ち上げる端末とlistenerを立ち上げる端末の計２つの端末が必要です。
### talker
以下のコードを実行してtalkerを立ち上げます。
```
$ ros2 run mypkg talker
```
talker自体は

### listener
```
$ ros2 run mypkg listener
```
* 出力結果
```
$
```
尚、先にtalkerを立ち上げていない場合は

### launch
launchファイルを使用することで、talkerとlistenerを一台で一度に実行することが可能です。
* コマンド
```
$ ros2 launch mypkg talk_listen.launch.py
```

## トピックについて

# テスト環境
Ubuntu 20.04

# ライセンス
* このソフトウェアパッケージは、3条項BSDライセンスの下、再頒布および使用が許可されます。
* © 2023 Yodai Shiota
