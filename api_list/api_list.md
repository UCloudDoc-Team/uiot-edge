# API列表



## 网关及子设备

| API名称                       | 描述               |
| ----------------------------- | ------------------ |
| [AddUIoTCoreSubDeviceTopo](./gateway_subdevice/AddUIoTCoreSubDeviceTopo)      | 添加子设备拓扑     |
| [DeleteUIoTCoreSubDeviceTopo](./gateway_subdevice/DeleteUIoTCoreSubDeviceTopo)   | 删除子设备拓扑     |
| [GetUIoTCoreEdgeList](./gateway_subdevice/GetUIoTCoreEdgeList)           | 获取边缘网关列表   |
| [GetUIoTCoreGatewayBySubDevice](./gateway_subdevice/GetUIoTCoreGatewayBySubDevice) | 获取子设备网关信息 |
| [GetUIoTCoreSubDeviceList](./gateway_subdevice/GetUIoTCoreSubDeviceList)      |获取子设备列表      |



## 安装及部署

| API名称                       | 描述                     |
| ----------------------------- | ------------------------ |
| [CreateUIoTCoreEdgeDeployment](./install_deploy/CreateUIoTCoreEdgeDeployment)  | 创建边缘部署任务         |
| [CreateUIoTCoreReinstall](./install_deploy/CreateUIoTCoreReinstall)       | 重装软件                 |
| [GetUIoTCoreReinstallInfo](./install_deploy/GetUIoTCoreReinstallInfo)      | 获取设备网关安装信息     |
| [GetUIoTCoreEdgeDeploymentList](./install_deploy/GetUIoTCoreEdgeDeploymentList) | 获取边缘部署任务列表     |
| [GetUIoTCoreEdgeDeploymentInfo](./install_deploy/GetUIoTCoreEdgeDeploymentInfo) | 获取边缘部署任务信息     |
| [GetUIoTCoreLatestEdgeDeploy](./install_deploy/GetUIoTCoreLatestEdgeDeploy)   | 获取最新边缘网关部署信息 |



## 子设备驱动与接入

| API名称                        | 描述                     |
| ------------------------------ | ------------------------ |
| [CreateUIoTCoreDriver](./subdev_driver_access/CreateUIoTCoreDriver)           | 创建驱动                 |
| [DeleteUIoTCoreDriver](./subdev_driver_access/DeleteUIoTCoreDriver)           | 删除驱动                 |
| [ModifyUIoTCoreDriver](./subdev_driver_access/ModifyUIoTCoreDriver)           | 修改驱动                 |
| [GetUIoTCoreDriverInfo](./subdev_driver_access/GetUIoTCoreDriverInfo)          | 获取驱动信息             |
| [GetUIoTCoreDriverList](./subdev_driver_access/GetUIoTCoreDriverList)          | 获取驱动列表             |
| [GetUIoTCoreDriverUpdateURL](./subdev_driver_access/GetUIoTCoreDriverUpdateURL)     | 获取驱动更新上传的URL    |
| [GetUIoTCoreDriverUploadURL](./subdev_driver_access/GetUIoTCoreDriverUploadURL)     | 获取驱动上传URL          |
| [CreateUIoTCoreEdgeDriverBind](./subdev_driver_access/CreateUIoTCoreEdgeDriverBind)   | 网关绑定驱动             |
| [CreateUIoTCoreMultiDriverBind](./subdev_driver_access/CreateUIoTCoreMultiDriverBind)  | 批量绑定网关和驱动       |
| [GetUIoTCoreEdgeDriverList](./subdev_driver_access/GetUIoTCoreEdgeDriverList)      | 获取网关绑定驱动列表     |
| [DeleteUIoTCoreEdgeDriverBind](./subdev_driver_access/DeleteUIoTCoreEdgeDriverBind)   | 删除网关和驱动绑定       |
| [GetUIoTCoreBindableProductList](./subdev_driver_access/GetUIoTCoreBindableProductList) | 获取可绑定产品列表       |
| [GetUIoTCoreBindableDeviceList](./subdev_driver_access/GetUIoTCoreBindableDeviceList)  | 获取可绑定设备列表       |
| [CreateUIoTCoreDriverSubDevBind](./subdev_driver_access/CreateUIoTCoreDriverSubDevBind) | 驱动绑定子设备           |
| [CreateUIoTCoreMultiSubDevBind](./subdev_driver_access/CreateUIoTCoreMultiSubDevBind)  | 批量创建驱动和子设备绑定 |
| [GetUIoTCoreDriverSubDevList](./subdev_driver_access/GetUIoTCoreDriverSubDevList)    | 获取驱动子设备列表       |
| [DeleteUIoTCoreDriverSubBind](./subdev_driver_access/DeleteUIoTCoreDriverSubBind)    | 删除驱动和子设备绑定     |
| [ModifyUIoTCoreEdgeDriverConf](./subdev_driver_access/ModifyUIoTCoreEdgeDriverConf)   | 修改网关驱动配置         |
| [ModifyUIoTCoreDriverSubDevConf](./subdev_driver_access/ModifyUIoTCoreDriverSubDevConf) | 修改驱动的子设备配置     |



## 添加函数计算

| API名称                        | 描述                 |
| ------------------------------ | -------------------- |
| [CreateUIoTCoreFunction](./edge_computing/CreateUIoTCoreFunction)         | 创建函数             |
| [DeleteUIoTCoreFunction](./edge_computing/DeleteUIoTCoreFunction)         | 删除函数             |
| [UpdateUIoTCoreFunction](./edge_computing/UpdateUIoTCoreFunction)         | 更新函数             |
| [GetUIoTCoreFunctionList](./edge_computing/GetUIoTCoreFunctionList)        | 获取函数列表         |
| [BindUIoTCoreFunctionToEdge](./edge_computing/BindUIoTCoreFunctionToEdge)     | 绑定函数至边缘网关   |
| [GetUIoTCoreEdgeFunctionList](./edge_computing/GetUIoTCoreEdgeFunctionList)    | 获取边缘网关函数列表 |
| [UnBindUIoTCoreFunctionFromEdge](./edge_computing/UnBindUIoTCoreFunctionFromEdge) | 将函数从边缘网关解绑 |


## 设置消息路由

| API名称                      | 描述             |
| ---------------------------- | ---------------- |
| [CreateUIoTCoreMessageRouter](./message_route/CreateUIoTCoreMessageRouter)  | 增加消息路由     |
| [DeleteUIoTCoreMessageRouter](./message_route/DeleteUIoTCoreMessageRouter)  | 删除消息路由     |
| [GetUIoTCoreMessageRouterList](./message_route/GetUIoTCoreMessageRouterList) | 获取消息路由列表 |
| [ModifyUIoTCoreMessageRouter](./message_route/ModifyUIoTCoreMessageRouter)  | 修改消息路由     |



## 远程运维管理

| API名称                       | 描述                     |
| ----------------------------- | ------------------------ |
| [GetUIoTCoreDeviceResourceData](./remote_maintaince/GetUIoTCoreDeviceResourceData) | 获取网关设备监控资源数据 |

