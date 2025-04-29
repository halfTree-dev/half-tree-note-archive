# ROS2的配置与基础概念

ROS2 是一个开源的机器人操作系统，提供了一系列工具和库来帮助开发者构建机器人应用。

## 配置过程

要完成在Linux上的ROS2安装，仅需参考这里的[官方教程](https://docs.ros.org/en/rolling/Installation/Ubuntu-Install-Debs.html#)即可。

安装完成后，记得将ROS2的环境变量添加到`.bashrc`中，在`~/.bashrc`中追加以下代码。

```bash
# Add ROS2 environment variables
source /opt/ros/rolling/setup.bash
```

完成后跑个小乌龟试试

```bash
ros2 run turtlesim turtlesim_node
```

## ROS2和ROS1的异同

ROS2 是一次对 ROS1 的重构，在保持了先前的项目框架的同时在设计上还有了很多改进。

### 相同点
1. 一个 ROS 项目仍然由多个节点组成，每个节点作为一个进程处理自己的业务。

### 不同点
1. roscore 不再是 ROS2 的核心组件，所有节点都可以独立运行，不需要依赖 roscore。
2. ROS2 使用 DDS 作为通信中间件，支持多种传输协议（如 UDP、TCP 等），而 ROS1 只支持 TCPROS。

