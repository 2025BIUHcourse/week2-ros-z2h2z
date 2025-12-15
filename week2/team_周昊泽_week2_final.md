# Week2 实验报告  
**姓名**：z2h2z 
**团队**：TEAM6
**日期**：2025-12-11  

---

## 1 实验目标
- [x] Linux 基础命令  
- [x] Python / C++ 环境搭建  
- [x] ROS1 Noetic 安装与验证  
- [x] Turtlesim 键盘 / 话题 / 程序控制  
- [x] 多乌龟 launch + rqt_graph 可视化  

---

## 2 环境信息
| 项目 | 版本 |
| ---- | ---- |
| Ubuntu | 20.04 |
| ROS | Noetic |
| Python | 3.8.10 |
| G++ | 9.4.0 |

---

## 3 实验过程与截图

### 3.1 Linux 基础
- 创建，移动及删除文件：`touch test.txt` 
  ![linux](./photo/linux1.png) 
  ![linux](./photo/linux5.png)
- 安装软件：`sudo apt install tree` 
  ![linux](./photo/linux3.png) 
- 进程管理：`ps aux | grep roscore`  
![linux](./photo/linux4.png)
![linux](./photo/linux2.png)

### 3.2 Python / C++ 环境
- Python HelloWorld：`python3 hello.py`
  ![python](./photo/python.png)   
- C++ 编译：`g++ -std=c++17 sum.cpp -o sum` 
 ![C++](./photo/c++.png)   
- VSCode 断点调试截图  
![vscode](./photo/VSCode1.png)
![vscode](./photo/VSCode2.png)
![vscode](./photo/VSCode3.png)

### 3.3 ROS 安装验证
- `roscore` 启动  
![roscore](./photo/roscore.png)
- `rosnode list`  
- 环境变量 `echo $ROS_DISTRO`  
![rosdistro](./photo/rosnode.png)

### 3.4 CATKIN 工作空间与功能包
- `catkin_make` 成功  
- `beginner_tutorials` 包  
- HelloWorld 节点运行  
![hello](./photo/hello.png)

### 3.5 Turtlesim 基础控制
#### 3.5.1 键盘控制
- `rosrun turtlesim turtle_teleop_key`  
#### 3.5.2 rostopic 直线
- `rostopic pub /turtle1/cmd_vel ...`  
![straight](./photo/t2.png)

#### 3.5.3 程序画圆
- 运行 `draw_circle.py`  
![circle](./photo/t4.png)

### 3.6 多乌龟 launch + rqt
-launch
![launch](./photo/launch.png)
#### 3.6.1 通信图
- `rqt_graph`   
![rqt_graph](./photo/rqt_graph.png)
- `rqt_plot`  
![rqt_plot](./photo/rqt_plot.png)

#### 3.6.2 双轨迹(rostopic pub 命令)
- turtle1 直线 + turtle2 转圈  
![rostopic pub 命令](./photo/rostopic1.png)
![rostopic pub 命令](./photo/rostopic2.png)

---
## 4. 问题

1. rosdep 更新失败
2. VSCode 无法断点
3. rqt_plot 无数据

## 5. 问题解决

1. 换热点+改 hosts
2. 在 .vscode/launch.json 里加 "externalConsole": false
3. 话题名称写错，用 rostopic list 确认应为 /t1/turtle1/pose/x

## 6. 模块理解

### 1 Linux 习惯养成
- 第一次用 apt+ps+kill 组合拳，体会到“一切接管道”的灵活；以后写脚本先 man 再 grep 更高效。
### 2 ROS 三层概念清晰化
- 工作空间（workspace）→ 功能包（package）→ 节点（node）。先搭框架再填代码，思路瞬间清晰。

