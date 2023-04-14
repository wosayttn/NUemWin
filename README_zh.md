# NUemWin

[English](README.md) | **中文**

## 1、介绍

Nuvoton MA35D1/N9H30/M467 系列免费为其用户提供经 SEGGER 正式授权，专为嵌入式系统打造的 GUI 软件链接库 ( emWin ) 和相关开发工具，让产品开发人员可以快速且容易地，开发出流畅、有质感的用户人机显示接口 ( Human Machine Interface, HMI ) ，为满足客户针对显示应用弹性设计的需求。

### 1.1 目录结构

| 名称 | 说明 |
| ---- | ---- |
| Config | 应用配置与显示驱动适配 |
| Examples | 例子目录，并有相应的一些说明 |
| Include  | 头文件目录 |
| Lib  | 库目录 |

### 1.2 许可证

- Licensor:                 SEGGER Software GmbH
- Licensed to:              Nuvoton Technology Corporation, No. 4, Creation Rd. III, Hsinchu Science Park, 30077 Hsinchu City, Taiwan
- Licensed SEGGER software: emWin
- License number:           GUI-00735
- License model:            emWin License Agreement, signed February 27, 2018
- Licensed platform:        Cortex-M and ARM9 32-bit series microcontroller designed and manufactured by or for Nuvoton Technology Corporation

### 1.3 依赖

- RT-Thread 4.0.5+

## 2、如何下载

请至新唐官网填写基本数据后，即可下载 NUemWin 图形库。
NUemWin 图形库下载后，解压缩**XXX_RTThread_emWin_Package.zip** 后，将其解压缩目录拷贝至 BSP packages 目录内，再进行编译。

| 各支持平台图形库下载地址 |
| ------ |
| [MA35D1](https://www.nuvoton.com/products/microprocessors/arm-cortex-a35-mpus/ma35d1-high-performance-edge-iiot-series/?group=Software&tab=2)|
| [N9H30](https://www.nuvoton.com/products/microprocessors/arm9-mpus/-n9h-series/?group=Software&rt=HMI%20Library&tab=2)|
| [M467](https://www.nuvoton.com/products/microcontrollers/arm-cortex-m4-mcus/m467-ethernet-crypto-series/?group=Software&rt=HMI+Library&tab=2)|

## 3、编译

由于 NUemWin 与 其它图形库 启动执行是互斥的。若要执行 NUemWin 的demo，需要把其它图形库(例如：LVGL)的选项关闭。需在 Env 内，执行 menuconfig 后，取消 LVGL 选项并且加入 NUemWin package，路径如下：

```bash
$ pkgs --upgrade

$ menuconfig
RT-Thread online packages  --->
  multimedia packages  --->
    LVGL: powerful and easy-to-use embedded GUI library  --->
      [ ] LVGL (official): Light and Versatile Graphics Library  --->
    [*] NUemWin: a NUemWin package for rt-thread  --->
    [*]   Enable NUemWin example
      Examples (GUIDemo)  --->

$ scons -c
$ scons -j 16
```

## 4、其它注意事项

具体 emWin API 说明 参照官方手册。
