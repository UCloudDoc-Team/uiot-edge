# API列表



## 网关及子设备

| API名称                       | 描述               |
| ----------------------------- | ------------------ |
| AddUIoTCoreSubDeviceTopo      | 添加子设备拓扑     |
| DeleteUIoTCoreSubDeviceTopo   | 删除子设备拓扑     |
| GetUIoTCoreEdgeList           | 获取边缘网关列表   |
| GetUIoTCoreGatewayBySubDevice | 获取子设备网关信息 |
| GetUIoTCoreSubDeviceList      |获取子设备列表      |



## 安装及部署

| API名称                       | 描述                     |
| ----------------------------- | ------------------------ |
| CreateUIoTCoreEdgeDeployment  | 创建边缘部署任务         |
| CreateUIoTCoreReinstall       | 重装软件                 |
| GetUIoTCoreReinstallInfo      | 获取设备网关安装信息     |
| GetUIoTCoreEdgeDeploymentList | 获取边缘部署任务列表     |
| GetUIoTCoreEdgeDeploymentInfo | 获取边缘部署任务信息     |
| GetUIoTCoreLatestEdgeDeploy   | 获取最新边缘网关部署信息 |



## 子设备驱动与接入

| API名称                        | 描述                     |
| ------------------------------ | ------------------------ |
| CreateUIoTCoreDriver           | 创建驱动                 |
| DeleteUIoTCoreDriver           | 删除驱动                 |
| ModifyUIoTCoreDriver           | 修改驱动                 |
| GetUIoTCoreDriverInfo          | 获取驱动信息             |
| GetUIoTCoreDriverList          | 获取驱动列表             |
| GetUIoTCoreDriverUpdateURL     | 获取驱动更新上传的URL    |
| GetUIoTCoreDriverUploadURL     | 获取驱动上传URL          |
| CreateUIoTCoreEdgeDriverBind   | 网关绑定驱动             |
| CreateUIoTCoreMultiDriverBind  | 批量绑定网关和驱动       |
| GetUIoTCoreEdgeDriverList      | 获取网关绑定驱动列表     |
| DeleteUIoTCoreEdgeDriverBind   | 删除网关和驱动绑定       |
| GetUIoTCoreBindableProductList | 获取可绑定产品列表       |
| GetUIoTCoreBindableDeviceList  | 获取可绑定设备列表       |
| CreateUIoTCoreDriverSubDevBind | 驱动绑定子设备           |
| CreateUIoTCoreMultiSubDevBind  | 批量创建驱动和子设备绑定 |
| GetUIoTCoreDriverSubDevList    | 获取驱动子设备列表       |
| DeleteUIoTCoreDriverSubBind    | 删除驱动和子设备绑定     |
| ModifyUIoTCoreEdgeDriverConf   | 修改网关驱动配置         |
| ModifyUIoTCoreDriverSubDevConf | 修改驱动的子设备配置     |



## 添加函数计算

| API名称                        | 描述                 |
| ------------------------------ | -------------------- |
| CreateUIoTCoreFunction         | 创建函数             |
| DeleteUIoTCoreFunction         | 删除函数             |
| UpdateUIoTCoreFunction         | 更新函数             |
| GetUIoTCoreFunctionList        | 获取函数列表         |
| BindUIoTCoreFunctionToEdge     | 绑定函数至边缘网关   |
| GetUIoTCoreEdgeFunctionList    | 获取边缘网关函数列表 |
| UnBindUIoTCoreFunctionFromEdge | 将函数从边缘网关解绑 |


## 设置消息路由

| API名称                      | 描述             |
| ---------------------------- | ---------------- |
| CreateUIoTCoreMessageRouter  | 增加消息路由     |
| DeleteUIoTCoreMessageRouter  | 删除消息路由     |
| GetUIoTCoreMessageRouterList | 获取消息路由列表 |
| ModifyUIoTCoreMessageRouter  | 修改消息路由     |



## 远程运维管理

| API名称                       | 描述                     |
| ----------------------------- | ------------------------ |
| EnableUIoTCoreDeviceRemoteSSH | 设备设备远程ssh开关      |
| GetUIoTCoreDeviceResourceData | 获取网关设备监控资源数据 |

