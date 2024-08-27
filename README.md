## �ο�
1. [`SystemView WIKI`](https://wiki.segger.com/Category:SystemView)
2. `SystemView`��װ·���£�`SystemView/Doc/UM08027_SystemView.pdf`

## ˵��
1. `SystemView target source code`;
2. ��Դ����Դ��`SystemView_Windows_V356(Rev.0)_x64.exe`��װ·���µ�`Src`�ļ��У�

## ʹ��
1. ͨ��`git submodule add https://github.com/ShadowThree/SystemView.git ThirdUtils/SystemView`��ӱ���Ŀ������ָ��Ŀ¼��
2. ��`RTOS`����ʹ����ο�[`SystemView NoOS Demo`](https://github.com/ShadowThree/SystemView_NoOS_Demo.git);
3. `FreeRTOS`����ʹ����ο�[`System FreeRTOS Demo`](https://github.com/ShadowThree/SystemView_FreeRTOS_Demo.git);

## ע��
1. ֻ����`ARM Compiler V5`����ֲ��
2. ��`SEGGER_SYSVIEW_Conf.h`��������¶��壺
```c
// ע�⣺�� SEGGER_SYSVIEW_ConfDefaults.h �ļ��У��Ѿ������¶��壺
// #define SEGGER_SYSVIEW_CORE_OTHER   0
// #define SEGGER_SYSVIEW_CORE_CM0     1 // Cortex-M0/M0+/M1
// #define SEGGER_SYSVIEW_CORE_CM3     2 // Cortex-M3/M4/M7
// #define SEGGER_SYSVIEW_CORE_RX      3 // Renesas RX

#define SEGGER_SYSVIEW_CORE	SEGGER_SYSVIEW_CORE_CM3     // STM32F429BI
```
3. ��`RTOS`�ͷ�`RTOS`������ʹ��ʱ��`SystemView`��ʼ�����õ�`API`��Щ��һ����
```c
// �� RTOS �����У�ֻ��Ҫ Conf ���ɣ�������û�� RTOS ����Ҫ��
SEGGER_SYSVIEW_Conf();

// ��������ֻ���ڷ� RTOS �����²���Ҫ
// SEGGER_SYSVIEW_Start();
// SEGGER_SYSVIEW_OnIdle();
```