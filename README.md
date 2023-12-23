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
さらに以下のコードを実行することで、事前準備が完了します。
```
$ cd ~/ros2_ws
$ colcon build
$ source ~/.bashrc
```

## 使用方法
### talkerとlistenerを個別で立ち上げる方法
こちらの方法では、talkerを立ち上げる端末とlistenerを立ち上げる端末の計２つの端末が必要です。
#### 実行手順
* 端末1で以下のコードを実行してtalkerを立ち上げます。
```
$ ros2 run mypkg talker
```
画面には何も表示されません。
* 端末2で以下のコードを実行し、listenerを立ち上げます。
```
$ ros2 run mypkg listener
```
* 出力結果
```

```

### launchで一度に立ち上げる方法
この方法では、talkerとlistenerを一つの端末で一度に実行することが可能です。
* コマンド
```
$ ros2 launch mypkg talk_listen.launch.py
```
* 出力結果
```
[listener-2] [INFO] [1703356758.452571533] [listener]: Listen: 0
[listener-2] [INFO] [1703356758.946440279] [listener]: Listen: 1
[listener-2] [INFO] [1703356759.446384256] [listener]: Listen: 2
[listener-2] [INFO] [1703356759.946393187] [listener]: Listen: 3
...
```

## トピック

# テスト環境
Ubuntu 20.04

# ライセンス
* このソフトウェアパッケージは、3条項BSDライセンスの下、再頒布および使用が許可されます。
* © 2023 Yodai Shiota
