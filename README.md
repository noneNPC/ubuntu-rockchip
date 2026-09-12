# Ubuntu Rockchip for Youyeetoo R1

适用于 Rockchip RK35XX 系列平台的 Ubuntu ARM64 镜像项目。

本项目基于开源项目：

https://github.com/SuperKali/ubuntu-rockchip

并针对 **Youyeetoo R1（Rockchip RK3588S）** 进行了定制和优化。

主要目标是提供一个适用于 **嵌入式开发、机器人、边缘计算以及 AI 应用** 的稳定 Ubuntu 环境。

---

## 项目简介

Ubuntu Rockchip 是一个面向 Rockchip ARM 平台的 Ubuntu 移植项目。

本仓库在原项目基础上进行了针对性修改，主要面向：

- Youyeetoo R1
- RK3588S 平台
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS

提供：

- ARM64 Ubuntu 系统镜像
- Rockchip BSP 内核支持
- U-Boot 启动支持
- Device Tree 配置
- 自动化镜像构建流程

---

## 支持设备

### Youyeetoo R1

| 项目 | 参数 |
| --- | --- |
| SoC | Rockchip RK3588S |
| CPU | 4 × Cortex-A76 + 4 × Cortex-A55 |
| GPU | Mali-G610 |
| NPU | Rockchip NPU |
| 架构 | ARM64 |
| 系统 | Ubuntu 22.04 / 24.04 |

---

## 镜像版本

目前支持两种系统版本：

### Desktop

适用于：

- 日常开发
- 图形界面应用
- ROS2开发
- AI视觉应用

包含：

- Ubuntu Desktop 环境
- 图形界面
- 常用开发工具


### Server服务器版

适用于：

- 无显示设备部署
- 机器人主机
- Docker容器
- 边缘计算

特点：

- 更小的系统体积
- 更低资源占用
- SSH远程管理

---

## 内核支持

本项目使用 Rockchip Linux 内核方案。

包含：

- Rockchip硬件驱动
- GPU相关支持
- 多媒体驱动
- NPU相关支持
- RK3588设备树配置


当前支持：

- Linux 5.10 BSP
- Linux 6.1 BSP（开发中）

---

## 镜像构建

### 本地构建

克隆仓库：

```bash
git clone https://github.com/noneNPC/ubuntu-rockchip.git

cd ubuntu-rockchip
```

构建 Youyeetoo R1 镜像：

```bash
sudo ./build.sh \
    --board=youyeetoo-r1 \
    --suite=jammy \
    --flavor=desktop
```

可选系统类型：

```
desktop
server
```

---

## GitHub Actions 自动构建

本项目提供 GitHub Actions 自动化构建支持。

构建流程：

```
Ubuntu RootFS生成
        |
        |
Kernel编译
        |
        |
镜像打包
        |
        |
生成ARM64镜像文件
```

可以通过 GitHub Actions 自动生成镜像。

---

## 相比上游项目的修改

本项目基于：

https://github.com/SuperKali/ubuntu-rockchip

进行了以下修改：

- 修改镜像构建流程
- 调整 GitHub Actions 工作流
- 删除不需要的目标设备
- 优化板级配置
- 删除不可用的GPU驱动源
- 添加可用源

---

## 许可证

本项目遵循 GPL-3.0 开源协议。

详细信息请查看：

```
LICENSE
```

本项目基于社区开源项目开发，并保留原项目许可证及版权信息。

感谢所有开源贡献者。