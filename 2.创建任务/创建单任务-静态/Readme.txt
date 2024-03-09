            大小
          /
任务栈 
          \
            起始地址


系统的运作流程：
		BSP_Iinit()
		创建任务
		启动调度器
		。。。。。。

创建单任务—SRAM静态内存
1. 定义任务函数
2. 空闲任务与定时器任务堆栈函数实现
3. 定义任务栈
4. 定义任务控制块
5. 静态创建任务
6. 启动任务

想要静态分配      FREERTOS_CONFIG_H 中宏 configSUPPORT_STATIC_ALLOCATION=1


当configSUPPORT_STATIC_ALLOCATION=1时一定要定义以下函数：
获取空闲任务的任务堆栈和任务控制块内存
void vApplicationGetIdleTaskMemory(StaticTask_t **ppxIdleTaskTCBBuffer, StackType_t **ppxIdleTaskStackBuffer, uint32_t *pulIdleTaskStackSize)

获取定时器任务的任务堆栈和任务控制块内存
void vApplicationGetTimerTaskMemory(StaticTask_t **ppxTimerTaskTCBBuffer, StackType_t **ppxTimerTaskStackBuffer, uint32_t *pulTimerTaskStackSize)

