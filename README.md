# robosys2023 ros2 talker listener

このレポジトリは、ロボットシステム学の課題2提出用リポジトリです。

[![test](https://github.com/yodaishiota/robosys2023_mypkg/actions/workflows/test.yml/badge.svg)](https://github.com/yodaishiota/robosys2023_mypkg/actions/workflows/test.yml)

## 機能について
パブリッシャーのtalkerとサブスクライバーのlistener間の通信の様子を確認する

## 事前準備
> ROS 2がインストールされていなければ最初にROS 2のインストールを行ってください。
>
> 以下のコードを実行し、ワークスペースを作成して本レポジトリをクローンしてください。
> ```
> $ mkdir -p ros2_ws/src
> $ cd ros2_ws/src
> $ git clone https://github.com/yodaishiota/mypkg.git
> ```
> さらに以下のコードを実行することで、事前準備が完了します。
> ```
> $ cd ~/ros2_ws
> $ colcon build
> $ source ~/.bashrc
> ```

## トピック
### countup

## ノード
### talker
実行すると、0.5秒間に1ずつカウントしてトピック/countupを通じてメッセージを送信します。

### listener
実行すると、countupからメッセージを受信し表示します。
## 使用方法
### talkerとlistenerを個別で立ち上げる方法
こちらの方法では、talkerを立ち上げる端末とlistenerを立ち上げる端末の計２つの端末が必要です。
#### 実行手順
> * 端末1で以下のコードを実行してtalkerを立ち上げます。
> ```
> $ ros2 run mypkg talker
> ```
> 画面には何も表示されません。
> * 端末2で以下のコードを実行し、listenerを立ち上げます。
> ```
> $ ros2 run mypkg listener
> ```
> * 出力結果
> ```
> [INFO] [1703359890.237488938] [listener]: Listen: 0
> [INFO] [1703359890.682477170] [listener]: Listen: 1
> [INFO] [1703359891.181948047] [listener]: Listen: 2
> [INFO] [1703359891.682177716] [listener]: Listen: 3
> [INFO] [1703359892.182472810] [listener]: Listen: 4
> ...
> ```
この結果が確認できれば正常に動作しています。

なお、カウントはtalkerを立ち上げた際から行われているので、listenerを立ち上げるタイミングによって表示される出力結果のカウントは変化します。

### launchで一度に立ち上げる方法
こちらの方法では、talkerとlistenerを一つの端末で一度に実行することが可能です。
> * コマンド
> ```
> $ ros2 launch mypkg talk_listen.launch.py
> ```
> * 出力結果
> ```
> [listener-2] [INFO] [1703356758.452571533] [listener]: Listen: 0
> [listener-2] [INFO] [1703356758.946440279] [listener]: Listen: 1
> [listener-2] [INFO] [1703356759.446384256] [listener]: Listen: 2
> [listener-2] [INFO] [1703356759.946393187] [listener]: Listen: 3
> ...
> ```
こちらの方法でも同様の動作が確認できます。

# 開発環境
Ubuntu 20.04
ROS 2 Foxy

# テスト環境
Ubuntu 22.04
ROS 2 Humble


# ライセンス
* このソフトウェアパッケージは、3条項BSDライセンスの下、再頒布および使用が許可されます。
* このパッケージのコードは、下記のスライド群 (CC-BY-SA 4.0 by Ryuichi Ueda) のlesson8,lesson10,lesson11のものを、本人の許可を得て自身の著作としたものです。
	* [ryuichiueda/my_slides robosys_2022](https://github.com/ryuichiueda/my_slides/tree/master/robosys_2022)
* © 2023 Yodai Shiota
