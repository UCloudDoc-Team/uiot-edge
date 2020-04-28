# 物联网边缘网关

UIoT Edge产品是UCloud IoT为工业、能源、楼宇等需要本地实时响应、就近计算、多协议接入的场景而提供的一套软件运行时，客户可以直接部署到符合要求的x86、arm硬件平台上，实现设备接入、边缘计算等功能。

UIoT Edge提供子设备接入、函数计算、消息路由、本地缓存断网续传、远程SSH运维，提供完整的边缘端解决方案。




命名规范：

1.产品名称：UIoT Core、UIoT Edge、UIoT SDK等

遗留问题：

1. 消息路由的唯一标识是name，而不是相同的源、topic、目的地；所以配置两条规则一样的，将会触发两次；


- <div class="sidebar_title icon__uiot">物联网边缘网关 UIoT Edge</div>
  
  - [产品简介](/uiot-edge/introduce/README.md)  
    - [什么是物联网边缘网关](/uiot-edge/introduce/iot_edge_introduce.md)
    - [功能介绍](/uiot-edge/introduce/functions.md)
    - [名词解释](/uiot-edge/introduce/glossary.md)
    - [产品计费模式](/uiot-edge/introduce/price.md)
  
  - [使用指南](/uiot-edge/user_guide/README.md)
    - [使用流程概述](/uiot-edge/user_guide/overview.md)
    - 创建网关及子设备
      - [创建网关](/uiot-edge/user_guide/edge_subdevice/create_edge.md)
      - [创建子设备](/uiot-edge/user_guide/edge_subdevice/create_subdevice.md)
      - [关联子设备](/uiot-edge/user_guide/edge_subdevice/subdevice_bind.md)
      - [网关管理](/uiot-edge/user_guide/edge_subdevice/edge_management.md)
    - 安装网关软件
      - [安装软件](/uiot-edge/user_guide/install/runtime_install.md)
    - 子设备驱动与接入
      - [概览](/uiot-edge/user_guide/subdevice_driver_access/overview.md)
      - [驱动开发及添加](/uiot-edge/user_guide/subdevice_driver_access/driver_development.md)
      - [分配驱动](/uiot-edge/user_guide/subdevice_driver_access/driver_allocate.md)
      - [子设备接入协议](/uiot-edge/user_guide/subdevice_driver_access/subdev_access_protocol.md)
    - 添加边缘计算
      - [概览](/uiot-edge/user_guide/edge_computing/overview.md)
      - [函数开发及添加](/uiot-edge/user_guide/edge_computing/function_development.md)
      - [运行函数计算](/uiot-edge/user_guide/edge_computing/function_running.md) 
    - 设置消息路由
      - [概览](/uiot-edge/user_guide/message_route/overview.md)
      - [添加消息路由](/uiot-edge/user_guide/message_route/add_msg_route.md)
      - [消息路由配置详解](/uiot-edge/user_guide/message_route/route_config_detail.md)    
    - 远程运维管理
      - [远程访问](/uiot-edge/user_guide/remote_maintaince/remote_access.md)
  
  - [边缘端开发](/uiot-edge/edge_devplopment/README.md)
    - 子设备驱动SDK  
      - [概述](/uiot-edge/edge_development/subdev_driver_SDK/overview.md) 
      - [Python3 SDK使用](/uiot-edge/edge_development/subdev_driver_SDK/python3_SDK_intro.md)
      - [官方Modbus驱动](/uiot-edge/edge_development/subdev_driver_SDK/offical_modbus_driver.md)
  
  - [云端API接口](/uiot-edge/api_list/README.md)  
    - [概述](/uiot-edge/api_list/overview.md)
    - [API列表](/uiot-edge/api_list/api_list.md)
  
  - [本地控制台操作](/uiot-edge/local_console/README.md)
    - [概览](/uiot-edge/local_console/overview.md)
    - [控制台详细操作](/uiot-edge/local_console/console_opration_detail.md)
  
  - 最佳实践 
    - [使用Modbus RTU获取温湿度](/uiot-edge/best_practices/get_temp_humi_with_offical_modbus.md)
  
  - 常见问题
    - [常见问题](/uiot-edge/faq/faq.md)
  
  - 版本更新
    - [版本更新记录](/uiot-edge/version_notes/version_notes.md)
  
  
