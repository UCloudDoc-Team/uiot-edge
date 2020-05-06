# 概述

UIoT Edge提供操作云端控制台的API，方便用户在业务中集成云平台管理边缘网关的功能，边缘网关管理API列表包括网关设备管理、网关子设备管理、驱动管理、函数计算管理、消息路由管理等。

UIoT Edge平台暂不提供对不同云端开发语言的SDK，对于有云端开发需求的可以参考该文档，或者参考UCloud SDK框架[UCloud SDK](https://github.com/ucloud?utf8=%E2%9C%93&q=SDK&type=&language=)，通过API SDK框架集成自己的业务。

# 关于API的接入

UIoT Edge 和 [UIoT Core（物联网通信云平台）](https://console.ucloud.cn/uiot)一样使用独立的[API调用网关](https://docs.ucloud.cn/uiot-core/product_introduction/available_region_url#%e5%9f%9f%e5%90%8d%e5%88%97%e8%a1%a8)，以满足客户的业务需求。UIoT Edge以及UIoT Core的API调用和UCloud官方API调用的流程完全一致，可以参考[UIoT Core 关于API的接入章节](https://docs.ucloud.cn/uiot-core/api_guide/api_guidehelp)介绍的API的接入流程，也可参考UCloud官方[API 文档综览](https://docs.ucloud.cn/api/summary/overview)。需要JAVA/GO/PHP/Python等语言的参考，可以参考UCloud SDK框架[UCloud SDK项目](https://github.com/ucloud?utf8=✓&q=SDK&type=&language=)。

- 接入示例参考：[UIoT Core 关于API的接入](https://docs.ucloud.cn/uiot-core/api_guide/api_guidehelp)。