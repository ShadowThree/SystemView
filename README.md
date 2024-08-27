## 参考
1. [`SystemView WIKI`](https://wiki.segger.com/Category:SystemView)
2. `SystemView`安装路径下：`SystemView/Doc/UM08027_SystemView.pdf`

## 说明
1. `SystemView target source code`;
2. 本源码来源于`SystemView_Windows_V356(Rev.0)_x64.exe`安装路径下的`Src`文件夹；

## 使用
1. 通过`git submodule add https://github.com/ShadowThree/SystemView.git ThirdUtils/SystemView`添加本项目到工程指定目录；
2. 非`RTOS`环境使用请参考[`SystemView NoOS Demo`](https://github.com/ShadowThree/SystemView_NoOS_Demo.git);
3. `FreeRTOS`环境使用请参考[`System FreeRTOS Demo`](https://github.com/ShadowThree/SystemView_FreeRTOS_Demo.git);

## 注意
1. 只能在`ARM Compiler V5`下移植；
2. 在`SEGGER_SYSVIEW_Conf.h`中添加如下定义：
```c
// 注意：在 SEGGER_SYSVIEW_ConfDefaults.h 文件中，已经有如下定义：
// #define SEGGER_SYSVIEW_CORE_OTHER   0
// #define SEGGER_SYSVIEW_CORE_CM0     1 // Cortex-M0/M0+/M1
// #define SEGGER_SYSVIEW_CORE_CM3     2 // Cortex-M3/M4/M7
// #define SEGGER_SYSVIEW_CORE_RX      3 // Renesas RX

#define SEGGER_SYSVIEW_CORE	SEGGER_SYSVIEW_CORE_CM3     // STM32F429BI
```
3. 在`RTOS`和非`RTOS`环境下使用时，`SystemView`初始化调用的`API`有些不一样：
```c
// 在 RTOS 环境中，只需要 Conf 即可（不管有没有 RTOS 都需要）
SEGGER_SYSVIEW_Conf();

// 以下两个只有在非 RTOS 环境下才需要
// SEGGER_SYSVIEW_Start();
// SEGGER_SYSVIEW_OnIdle();
```