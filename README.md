# 自动驾驶汽车的轨迹跟踪运动控制

![Github Stars](https://badgen.net/github/stars/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking?icon=github&label=stars)
![Github Forks](https://badgen.net/github/forks/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking?icon=github&label=forks)

## 项目概述

<p align="justify">该项目专注于使用 CARLA 仿真器对自动驾驶车辆进行轨迹跟踪控制。为了实现车辆的横向和纵向控制，项目中使用 Python 实现了各种控制算法。
</p>

以下是已实现的控制器列表：

- 横向控制器:
  - Bang-Bang 控制器
  - PID 控制器
  - Pure-Pursuit控制器
  - Stanley 控制器
  - Proximally Optimal Predictive (POP) 控制器
- 纵向控制器:
  - PID 控制器
  - Adaptive Longitudinal 控制器 (ALC)

|                  | **ALC**                                  | **PID**                                  |
| ---------------- | ---------------------------------------- | ---------------------------------------- |
| **Bang Bang**    | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/ALC%20-%20Bang-Bang.gif) | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/PID%20-%20Bang-Bang.gif) |
| **PID**          | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/ALC%20-%20PID.gif) | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/PID%20-%20PID.gif) |
| **Pure Pursuit** | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/ALC%20-%20Pure-Pursuit.gif) | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/PID%20-%20Pure-Pursuit.gif) |
| **Stanley**      | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/ALC%20-%20Stanley.gif) | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/PID%20-%20Stanley.gif) |
| **POP**          | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/ALC%20-%20POP.gif) | ![](https://github.com/Tinker-Twins/Self_Driving_Car_Trajectory_Tracking/blob/main/Media/PID%20-%20POP.gif) |

## File Description

- `Waypoints.txt` 承载整个任务的参考轨迹。
- `Controller.py` 用于实现横向和纵向控制器以追踪轨迹。
- `Drive.py` 存储仿真参数，与模拟器连接，并运行整个运动控制流程以实现自主轨迹追踪。
- `Live_Plotter.py` 生成并实时更新车辆状态和轨迹的图表。
- `Controller Performance Analysis.ipynb` 用于根据追踪指标和延迟来分析控制器的性能。
- `Results` 该目录存储了完整的轨迹追踪任务的结果，以图表和日志文件的形式呈现。

## 使用



**1. 根据[链接](https://github.com/carla-simulator/carla/releases/tag/0.9.14) 下载Carla环境，然后创建Python 3.7的虚拟环境。**

```shell
pip install -r requirements.txt
pip install matplotlib==2.2.2
```

**2. 导航至 CARLA 可执行程序目录，比如：**

*Windows:*

```bash
> cd C:/CARLA
```

*Ubuntu:*

```
$ cd $HOME/CARLA
```

**3. 打开CARLA仿真器**

*Windows:*

```bash
CarlaUE4.exe 
```

*Ubuntu:*

```bash
$ ./CarlaUE4.sh 
```

航点是在默认Town10地图选取，使用默认地图测试！！！

**4. 运行脚本，选择合适的控制器**

*Windows:*

```bash
> python Drive.py --Longitudinal-Controller: {PID, ALC} --Lateral-Controller: {BangBang, PID, PurePursuit, Stanley, POP}
```

*Ubuntu:*

```bash
$ python Drive.py --Longitudinal-Controller: {PID, ALC} --Lateral-Controller: {BangBang, PID, PurePursuit, Stanley, POP}
```

这里推荐使用默认的控制器，不添加参数运行脚本！

## Citation

- We encourage you to cite the [following chapter](https://arxiv.org/abs/2011.08729) when using this repository for your research:

  ```bibtex
  @eprint{Control-Strategies-2021,
        title={Control Strategies for Autonomous Vehicles}, 
        author={Chinmay Vilas Samak and Tanmay Vilas Samak and Sivanathan Kandhasamy},
        year={2021},
        eprint={2011.08729},
        archivePrefix={arXiv},
        primaryClass={cs.RO}
  }
  ```

  This work has been published as 2nd Chapter of the book entitled **Autonomous Driving and Advanced Driver-Assistance Systems (ADAS): Applications, Development, Legal Issues, and Testing.** The publication can be found on [CRC Press](https://www.taylorfrancis.com/books/edit/10.1201/9781003048381/autonomous-driving-advanced-driver-assistance-systems-adas-lentin-joseph-amit-kumar-mondal).


- We specifically encourage you to cite the [following paper](https://arxiv.org/abs/2103.13240) when using the POP control algorithm for your research:

  ```bibtex
  @eprint{POP-Controller-2021,
        title={Proximally Optimal Predictive Control Algorithm for Path Tracking of Self-Driving Cars}, 
        author={Chinmay Vilas Samak and Tanmay Vilas Samak and Sivanathan Kandhasamy},
        year={2021},
        eprint={2103.13240},
        archivePrefix={arXiv},
        primaryClass={cs.RO}
  }
  ```

  This work has been published in **AIR2021: Advances in Robotics - 5th International Conference of The Robotics Society.** The publication can be found on [ACM Digital Library](https://dl.acm.org/doi/10.1145/3478586.3478632).
