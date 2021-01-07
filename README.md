# robot_system2

# ROSを利用して亀を動かす
亀を早く走らせ、壁に当たる前に旋回するようにした。

# 環境
- Ubuntu18.04LTS
- ROS(Melodic)
- Python 2.7.17
- XLaunch

# ROSのインストール
下記の資料に従って環境構築しました。
- [参考動画(~32:10まで)](https://www.youtube.com/watch?v=AFSrcE3qFkU)
- [インストーラ](https://github.com/ryuichiueda/ros_setup_scripts_Ubuntu18.04_desktop.git)


# パッケージ
```
$ cd ~/catkin_ws/src
$ git clone https://github.com/ikeda-hitomi/mypkg.git
$ cd ..
$ catkin_make
```
# 亀を走らせる
XLaunchを予め起動し以下を実行する。
```
$ roscore
$ rosrun turtlesim turtlesim_node
```
速く走らせる場合は
```
$ rosrun mypkg turtle.py cm=/turtle1/cmd_vel pose:=/turtle1/pose
```
遅く走らせる場合は
```
$ rosrun mypkg slow.py cm=/turtle1/cmd_vel pose:=/turtle1/pose
```
を実行する。もし壁に当たった場合、警告が表示される。

# キーボード操作で自由に亀を動かす
```
$ roscore
$ rosrun turtlesim turtlesim_node
$ rosrun turtlesim turtle_teleop_key
```
上記と同様で壁に当たった場合、警告が表示される。
キーボードの←↑→↓で操作

# 動作動画
以下より視聴できます。  
- [速く走らせる](https://youtu.be/JKBOvewLHmA)
- [遅く走らせる](https://youtu.be/tPKpvd6Urs4)

# ライセンス
このリポジトリは[BSD 3-Clause License](https://github.com/ikeda-hitomi/mypkg/blob/main/LICENSE)が付与されています。

# 参考文献
[ロボットシステム学第10回(ROS)](https://ryuichiueda.github.io/robosys2020/lesson10_ros.html#/)
[turtleを動かす](https://brain.cc.kogakuin.ac.jp/~kanamaru/lecture/ROS/index3.html)
