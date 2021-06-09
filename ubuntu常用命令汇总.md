### 常用的命令汇总
1.打开下载源列表

> sudo gedit /etc/apt/sources.list

` sudo gedit /etc/apt/sources.list `

```c++
sudo gedit /etc/apt/sources.list 
```



### LOAM

1.运行

```
roslaunch loam_velodyne loam_velodyne.launch
```

2.播放bag

```
rosbag play ~/nsh_indoor_outdoor.bag
or
rosbag play ./nsh_indoor_outdoor.bag
```





# ROS

1.运行一个master

```
roscore
```

2.运行海龟节点

```
rosrun turtlesim turtlesim_node
```

3.运行键盘控制节点

```
rosrun turtlesim turtle_teleop_key
```

4.查看话题与节点

```
rosrun rqt_graph rqt_graph
```



5.启动发布器

```
rosrun beginner_tutorials talker
```

6.启动订阅器

```
rosrun beginner_tutorials listener
```















