# Box Bot 2

## 概要

このパッケージは単一のGazeboのワールドに複数の軽量なロボットをシミュレーションするためにつくりました。Turtlebotではうまく表現されていなかったtfツリーも修正し、共通のマップを持ちつつ、それ以下でロボットそれぞれのツリーを持つようになっています。よって、Rviz上でもそれぞれの位置がMapを中心に表示されます。
ROS_CENTRAL_SERVERSパッケージを組み合わせることでブラウザから複数のロボットを表示させ、それぞれにコマンドを送ることができます。

## 機能

複数ロボットを単一のワールドに表示
シンプルなurdf
各ロボットのナビゲーションスタック



## インストール

### 前提条件

- ROS2 humble

- sim_worlds2がワークスペース内に存在する
## 使い方
例）shビルにBOX_BOTを二台出現させ、それぞれ自立走行可能な状態にする

1.Gazeboワールドを作り、Box_botを出現させる

```
 ros2 launch box_bot2_gazebo main_two_robots_sh.launch.xml
```

2. 二台用のナビゲーションを開始する
```
 ros2 launch box_bot2_navigation two_box_bots_navigation2.launch.xml
```
*デフォルトでは、Rvizはオフになっていますが、box_bot2_planner_server内のtwo_box_bots_pathplanner.launch.pyのコメントアウトされているものを戻せばそれぞれのロボット用のRVIZが表示されます。


## カスタマイズ

Box Bot 2は、モジュール式の設計がされています。`config`フォルダ内の設定ファイルを編集することで、その機能を簡単に拡張または変更できます。

## ライセンス

Box Bot 2は、MITライセンスでリリースされています。詳細については`LICENSE`ファイルを参照してください。

## 作者

大島　航


