# 概览

UIoT Edge能够提供云边协同的能力，在云平台直接添加子设备驱动、函数计算、消息路由等资源，然后同步到相应的边缘网关。

同时对于某些不能联网的场景或本地需要临时修改的场景，边缘网关提供本地控制台帮助管理网关的资源与配置：

- 在线设备：查看当前在线的子设备，指调用了[驱动SDK](/uiot-edge/edge_development/subdev_driver_SDK/python3_SDK_intro)中的`SubDevice.login`方法，离线设备不做显示；
- 驱动管理：管理已经部署到网关的设备，支持本地添加，但不支持同步给云端；
- 函数计算：管理已经部署到网关的函数计算，支持本地添加，但不支持同步给云端；
- 消息路由：管理已经部署到网关的消息路由规则，支持本地添加，但不支持同步给云端；

**云端控制台和本地控制台的使用注意事项**

1. 云端控制台的修改（设备驱动、函数计算、消息路由）可以通过部署同步到网关；

2. 本地控制台的修改无法同步到云平台；

3. 云平台重新部署会覆盖和本地修改有冲突的配置；

   

## UIoT Edge本地控制台使用流程

1. 参考[安装软件](/uiot-edge/user_guide/install/runtime_install)，在目标硬件上安装UIoT Edge运行时；
2. 访问本地控制台，http://local-ip:8080/admin；
3. 本地管理边缘网关：[在线设备](/uiot-edge/local_console/console_opration_detail#管理在线设备)、[驱动管理](/uiot-edge/local_console/console_opration_detail#驱动管理)、[函数计算](/uiot-edge/local_console/console_opration_detail#函数计算)、[消息路由](/uiot-edge/local_console/console_opration_detail#消息路由)；

![本地控制台](../images/本地控制台.png)