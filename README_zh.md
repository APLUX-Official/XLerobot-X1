# XLerobot-X1

## 项目概述

XLerobot-X1 是一个基于高通 QCS8550 边缘计算设备的低成本双臂移动机器人平台，专为具身智能研究设计。通过系统化设计和开源社区协作，该平台以近 5,000 元的成本实现了实用的双臂操作能力，为具身智能研究开辟了新的可能性。

![hajimi1](images_intro/hajimi1.png)
![feng1](images_intro/feng1.jpg)
![fengmian1](images_intro/fengmian1.png)

## 核心设计理念

1. **模块化与可扩展性设计**
   - 标准化接口：定义了机械和电气接口，实现移动平台和操作臂的独立开发和升级
   - 软硬件解耦：控制系统采用分层架构，分离上层任务规划和下层运动控制
   - 渐进式能力扩展：允许研究人员根据特定需求增量添加传感器、执行器等组件

2. **成本优化与性能平衡**
   - 优化材料选择：90% 的组件通过 3D 打印，结合高性价比电机和电子部件
   - 工作空间优化：通过机械结构设计最大化 SO101 机械臂的有效工作范围（约 40 cm）
   - 优化控制策略：采用蓝牙控制解决方案，避免 WiFi/5G 通信的高成本

3. **安全性与可靠性设计**
   - 物理安全设计：低扭矩电机、短臂长和轮式底座确保系统对人类的物理风险最小
   - 控制安全机制：软件对运动范围、速度和力施加限制，防止意外操作
   - 故障安全设计：关键系统采用冗余设计，确保单个故障不会导致整个系统故障

## 核心技术分析

1. **机械结构与运动学设计**
   - 配备双 SO-101 机械臂，每个臂具有 6 自由度，单臂负载能力为 600-1000 g
   - 通过优化臂长和关节配置最大化工作范围，满足家庭场景中的基本操作需求
   - 应用拓扑优化技术到 3D 打印部件，减轻重量同时确保结构强度

2. **控制系统架构**
   - 下层运动控制层：通过 Rhino Pi X1（基于 QCS8550 平台）进行实时控制
   - 中层任务执行层：实现任务分解和运动轨迹生成
   - 上层决策与学习层：集成 AI 模型，支持视觉感知、任务规划和学习

3. **传感器融合与感知系统**
   - 多模态感知：融合视觉、深度、触觉等传感器数据，增强环境理解能力
   - 轻量级处理：在边缘计算设备上实现高效感知算法
   - 仿真到现实迁移：通过 Maniskill 仿真环境支持快速算法验证和迁移

## 快速入门指南

1. **阅读 `Introduction.md` 文件**：了解项目风格和内容，包含高通版本 XLeRobot 的功能描述
2. **查看 `Principle` 文档**：快速浏览以获得对基本原理的理解
3. **审查 `Hardware_List` 文档**：列出项目所需的所有硬件组件和购买链接
4. **检查 `3D_Printing_Models` 文件夹**：包含项目的所有可打印部件
5. **浏览 `Assembly_Steps_and_Structure_Diagram` 文件夹**：包含机械臂、底盘和顶部安装的组装说明
6. **观看安装教程视频** [3D打印机械臂安装完整教程](https://www.bilibili.com/video/BV14UfeB9ErT/?share_source=copy_web&vd_source=a0b758095cb5fcb77af22d495bca8199)
7. **研究 `Wiring_Diagram` 文件夹**：了解如何连接所有组件
8. **完成硬件组装和接线后**：参考 `Set_Servo_ID` 文件夹，了解如何设置和编号所有伺服电机的 ID
9. **完成所有硬件工作后**：进入 `Code_Resources` 文件夹获取软件级说明

## 代码资源

XLerobot-X1 代码资源基于 XLeRobot 项目，提供了统一的机器人开发平台，包括：

- 机器人控制和远程操作
- 计算机视觉和感知
- 机器学习和强化学习
- 仿真环境
- 数据收集和处理
- 电机控制和校准

### 项目结构

```
lerobot/
├── examples/           # 示例脚本和演示
├── src/                # 源代码
│   └── lerobot/        # 主包
│       ├── async_inference/    # 策略执行的异步推理
│       ├── cameras/            # 相机模块和接口
│       ├── configs/            # 配置管理
│       ├── datasets/           # 数据集处理
│       ├── envs/               # 仿真环境
│       ├── motors/             # 电机控制和校准
│       ├── optim/              # 训练优化工具
│       ├── policies/           # 策略实现
│       ├── rl/                 # 强化学习工具
│       ├── robots/             # 机器人实现
│       ├── scripts/            # 命令行脚本
│       ├── teleoperators/      # 远程操作接口
│       ├── transport/          # 通信工具
│       ├── utils/              # 通用工具函数
│       ├── __init__.py         # 模块初始化
│       └── __version__.py      # 版本信息
├── .gitignore          # Git 忽略文件
├── LICENSE             # 许可证文件
├── README.md           # README 文件
├── README_zh.md        # 中文 README 文件
├── pyproject.toml      # 项目配置
└── requirements.txt    # 依赖项
```

## 应用场景

1. **学术研究场景**
   - 具身 AI 基础研究：研究物理交互和环境适应等核心问题
   - 算法验证：为验证新的控制和学习算法提供低成本环境
   - 跨学科研究：促进机器人学、AI、认知科学等领域的跨学科研究

2. **教育应用场景**
   - STEM 教育：为高中教育者提供前沿机器人技术的实践平台
   - 高等教育：作为大学机器人和 AI 课程的高性价比平台
   - 学生研究：支持从初学者到高级研究人员的完整学习路径

3. **家庭应用场景**
   - 日常家务协助：执行简单的家务，如物品递送和基本整理
   - 家庭自动化：作为智能家居系统的物理交互接口
   - 安全监控：结合视觉系统实现基本的家庭安全监控

4. **商业应用场景**
   - 产品原型开发：使用世界上最经济实惠的模块化机器人平台实现更快的原型开发
   - 技术验证：在低成本环境中验证新技术的可行性
   - 市场探索：探索家庭机器人市场的潜在需求和应用场景

## 开始使用

### 安装 Joy-Con 驱动

```bash
# 克隆仓库
git clone https://github.com/box2ai-robotics/joycon-robotics.git
cd joycon-robotics
pip install -e .
sudo apt-get update

sudo apt-get install -y libevdev-dev libudev-dev cmake

# 在运行 make install 之前，执行以下步骤：
# 1. 打开 Makefile 并从倒数第二行移除 'install_nintendo'，然后保存
# 2. 创建临时目录
mkdir /tmp/joycon-install-temp
# 3. 执行安装
make install

# 安装依赖
pip install lerobot

# 安装伺服电机控制库
pip install feetech-servo-sdk==1.0.0
```

### 基础使用

#### 示例代码启动

在 `Code_Resources/XLeRobot-X1/examples/` 目录中提供了示例代码，可按以下方式启动：

```bash
# Joy-Con控制器测试
python 1_test_joycon.py

# XLeRobot 3Wheels远程操作
python 7_xlerobot_3wheels_teleop_joycon.py

# XLeRobot 3Wheels校准工具
python 7b_xlerobot_3wheels_calibration.py
```

## 板级特定配置

### Rhino Pi-X1 配置

- **系统设置**：推荐 Ubuntu 22.04 以获得最佳性能
- **电源管理**：确保使用足够功率的电源适配器（推荐 12V/3A 或更高）
- **散热**：长期运行建议使用冷却风扇或散热片
- **接口配置**：
  - 机械臂控制：使用 UART 接口
  - 相机连接：使用 CSI 接口
  - 网络连接：使用千兆以太网或 Wi-Fi 6

### 性能优化

- **AI 推理**：利用高通 QCS8550 的 NPU 加速
- **视频处理**：使用 Adreno 740 GPU 进行图像处理
- **多线程**：充分利用 6 核 CPU 架构

## 贡献指南

欢迎对 XLerobot-X1 项目做出贡献！请参阅贡献指南了解更多信息。

## 许可证

XLerobot-X1 以 MIT 许可证发布。
