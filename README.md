# NUemWin for RT-Thread

## **Introduction**

The MA35D1/N9H30/M467 series comes with licensed industrial leading emWin embedded GUI library, which contains emWin library, samples, tools and documents. Nuvoton licensed it from SEGGER to allow developers to create smooth, professional, high quality Human Machine Interfaces ( HMI ) quickly and efficiently on these series free of charge.

### **License**

- Licensor:                 SEGGER Software GmbH
- Licensed to:              Nuvoton Technology Corporation, No. 4, Creation Rd. III, Hsinchu Science Park, 30077 Hsinchu City, Taiwan
- Licensed SEGGER software: emWin
- License number:           GUI-00735
- License model:            emWin License Agreement, signed February 27, 2018
- Licensed platform:        Cortex-M, Cortex-A35 and ARM9 32-bit series microcontroller designed and manufactured by or for Nuvoton Technology Corporation

### **Dependency**

- RT-Thread 4.0.5+

### **Folder Structure**

  | Name | Description |
  | ---- | ---- |
  | Config | Application and driver configuration |
  | Examples | Example folder |
  | Include  | emWin Header files. |
  | Lib  | Prebuilt libraries |

### **NuMaker-HMI-MA35D1**

- [Download Package](https://www.nuvoton.com/products/microprocessors/arm-cortex-a35-mpus/ma35d1-high-performance-edge-iiot-series/?group=Software&tab=2)

  After downloading and extracting **MA35D1_RTThread_emWin_Package.zip**, to copy **MA35D1_RTThread_emWin_Package** folder into **packages** as below.

  ```bash
  <path-to-rtthread>/bsp/nuvoton/numaker-hmi-ma35d1/packages/MA35D1_RTThread_emWin_Package
  ```

### **NuMaker-HMI-N9H30**

- [Download Package](https://www.nuvoton.com/products/microprocessors/arm9-mpus/-n9h-series/?group=Software&rt=HMI%20Library&tab=2)

  After downloading and extracting **N9H30_RTThread_emWin_Package.zip**, to copy **N9H30_RTThread_emWin_Package** folder into **packages** as below.

  ```bash
  <path-to-rtthread>/bsp/nuvoton/nk-n9h30/packages/N9H30_RTThread_emWin_Package
  ```

### **NuMaker-HMI-M467**

- [Download Package](https://www.nuvoton.com/products/microcontrollers/arm-cortex-m4-mcus/m467-ethernet-crypto-series/?group=Software&rt=HMI+Library&tab=2)

  After downloading and extracting **M467_RTThread_emWin_Package.zip**, to copy **M467_RTThread_emWin_Package** folder into **packages** as below.

  ```bash
  <path-to-rtthread>/bsp/nuvoton/numaker-m467hj/packages/M467_RTThread_emWin_Package
  ```

## **Build**

  Before building rt-thread with NUemWin, to select NUemWin package using menuconfig.

  ```bash
  $ cd <path-to-rtthread>/bsp/nuvoton/<board-name>/
  $ pkgs --upgrade

  $ menuconfig
  RT-Thread online packages  --->
    multimedia packages  --->
      [*] NUemWin: a NUemWin package for rt-thread  --->
      [*]   Enable NUemWin example
        Examples (GUIDemo)  --->

  $ pkgs --update
  $ scons -c
  $ scons -j 16
  ```

## **Deploy**

  Please refer README.md in board folder.

  ```bash
  Path: <path-to-rtthread>/bsp/nuvoton/<board-name>/README.md
  ```

## 4. **Others**

- Execution at startup

    Due to NUemWin example and others execution is exclusive. If you want to run NUemWin demo on a board, you should cancel other HMI demo options(like LVGL) and include NUemWin package option. See below steps.

  ```bash
  $ menuconfig
  RT-Thread online packages  --->
    multimedia packages  --->
      LVGL: powerful and easy-to-use embedded GUI library  --->
        [ ] LVGL (official): Light and Versatile Graphics Library  --->
      [*] NUemWin: a NUemWin package for rt-thread  --->
      [*]   Enable NUemWin example
        Examples (GUIDemo)  --->
  ```
