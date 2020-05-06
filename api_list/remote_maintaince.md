# 远程运维管理


## GetUIoTCoreDeviceResourceData

获取网关设备监控资源数据

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|产品序列号|**Yes**|
|DeviceSN|string|设备序列号|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UsagePercent|object|资源使用百分百|**Yes**|

### DeviceResourceUsagePercent
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CPU|double|CPU使用率|**Yes**|
|Memory|double|内存使用率|**Yes**|
|Disk|double|磁盘使用率|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreDeviceResourceData
&Region=cn-zj
&ProjectId=pqSkJqyj
&ProductSN=oXYlQMLQ
&DeviceSN=xiEpzqwI
```

### 响应示例
```
{
    "UsagePercent": {}, 
    "Action": "GetUIoTCoreDeviceResourceDataResponse", 
    "RetCode": 0
}
```


