# 网关及子设备

## AddUIoTCoreSubDeviceTopo

添加子设备拓扑

### 请求参数	
| Parameter name | Type   | Description                                                  | Required |
| -------------- | ------ | ------------------------------------------------------------ | -------- |
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
| ProjectId      | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) | No       |
| GWProductSN    | string | 网关产品序列号                                               | **Yes**  |
| GWDeviceSN     | string | 网关设备序列号                                               | **Yes**  |
| DevProductSN   | string | 设备产品序列号                                               | **Yes**  |
| DevDeviceSN.n  | string | 设备序列号                                                   | **Yes**  |

### 响应参数
| Parameter name | Type   | Description | Required |
| -------------- | ------ | ----------- | -------- |
| RetCode        | int    | 返回码      | **Yes**  |
| Action         | string | 操作名称    | **Yes**  |

### 请求示例
```
https://api.ucloud.cn/?Action=AddUIoTCoreSubDeviceTopo
&Region=cn-zj
&ProjectId=JtYpQwpO
&GWProductSN=cenmtDXW
&DevProductSN=BzWTYCOx
&DeviceSN.n=QAkvRbyv
&GWDeviceSN=WcWkKkOI
```

### 响应示例
```
{
    "Action": "AddUIoTCoreSubDeviceTopoResponse", 
    "RetCode": 0
}
```



## DeleteUIoTCoreSubDeviceTopo

删除子设备拓扑

### 请求参数
| Parameter name | Type   | Description                                                  | Required |
| -------------- | ------ | ------------------------------------------------------------ | -------- |
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
| ProjectId      | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) | No       |
| ProductSN      | string | 子设备产品序列号                                             | **Yes**  |
| DeviceSN.n     | string | 子设备设备序列号                                             | **Yes**  |

### 响应参数
| Parameter name | Type   | Description | Required |
| -------------- | ------ | ----------- | -------- |
| RetCode        | int    | 返回码      | **Yes**  |
| Action         | string | 操作名称    | **Yes**  |

### 请求示例
```
https://api.ucloud.cn/?Action=DeleteUIoTCoreSubDeviceTopo
&Region=cn-zj
&ProjectId=JWeKpbVr
&ProductSN=cKazuvmE
&DeviceSN=xrNVpPXc
```

### 响应示例
```
{
    "Action": "DeleteUIoTCoreSubDeviceTopoResponse", 
    "RetCode": 0
}
```

## GetUIoTCoreEdgeList

获取边缘网关列表

### 请求参数
| Parameter name | Type   | Description                                                  | Required |
| -------------- | ------ | ------------------------------------------------------------ | -------- |
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
| ProjectId      | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) | No       |
| ProductSN      | string | 设备序列号                                                   | **Yes**  |
| DeviceSN       | string | 设备SN，如提供则按照当前字段模糊查询                         | No       |
| Offset         | int    | 列表起始位置偏移量，默认为0                                  | No       |
| Limit          | int    | 返回数据长度，默认为20，最大100                              | No       |

### 响应参数
| Parameter name | Type   | Description | Required |
| -------------- | ------ | ----------- | -------- |
| RetCode        | int    | 返回码      | **Yes**  |
| Action         | string | 操作名称    | **Yes**  |
| TotalCount     | int    | 记录总数    | **Yes**  |
| EdgeList       | array  | Edge列表    | **Yes**  |

## Edge
| Parameter name         | Type   | Description         | Required |
| ---------------------- | ------ | ------------------- | -------- |
| CPUArch                | string | CPU架构             | **Yes**  |
| SoftwareVersion        | string | 软件版本            | **Yes**  |
| OS                     | string | 操作系统            | **Yes**  |
| Mode                   | string | 部署模式            | **Yes**  |
| DeviceSN               | string | 设备序列号          | No       |
| ProductSN              | string | 所属产品序列号      | No       |
| Description            | string | 设备描述            | No       |
| Password               | string | 密码                | No       |
| Status                 | string | 设备状态            | No       |
| CreateTime             | int    | 创建时间            | No       |
| ActiveTime             | int    | 设备激活时间        | No       |
| LatestOnlineTime       | int    | 最近一次上线时间    | No       |
| LatestOfflineTime      | int    | 最近一次下线时间    | No       |
| IPAddr                 | string | 设备IP              | No       |
| RemoteSSHOpen          | bool   | 远程SSH开关是否打开 | No       |
| RemoteSSHPort          | int    | 远程SSH端口         | No       |
| LatestDeploymentStatus | string | 部署状态            | No       |
| LatestDeploymentTime   | int    | 最近部署时间        | No       |

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreEdgeList
&Region=cn-zj
&ProjectId=OlWzAUtb
&ProductSN=RqsCwWRv
&DeviceSN=UDNaKgeo
&Offset=9
&Limit=1
```

### 响应示例
```
{
    "Action": "GetUIoTCoreEdgeListResponse", 
    "TotalCount": 4, 
    "EdgeList": [
        "EcICEkqn"
    ], 
    "RetCode": 0
}
```

## GetUIoTCoreGatewayBySubDevice

获取子设备网关信息

### 请求参数
| Parameter name | Type   | Description                                                  | Required |
| -------------- | ------ | ------------------------------------------------------------ | -------- |
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
| ProjectId      | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list) | No       |
| ProductSN      | string | 子设备产品序列号                                             | **Yes**  |
| DeviceSN       | string | 子设备设备序列号                                             | **Yes**  |

### 响应参数
| Parameter name | Type   | Description | Required |
| -------------- | ------ | ----------- | -------- |
| RetCode        | int    | 返回码      | **Yes**  |
| Action         | string | 操作名称    | **Yes**  |
| Gateway        | object | 网关信息    | **Yes**  |

## GatewayInfo
| Parameter name | Type   | Description | Required |
| -------------- | ------ | ----------- | -------- |
| ProductSN      | string | 产品序列号  | **Yes**  |
| DeviceSN       | string | 设备序列号  | **Yes**  |
| ProductName    | string | 产品名称    | **Yes**  |

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreGatewayBySubDevice
&Region=cn-zj
&ProjectId=dmiYIcLp
&ProductSN=szmboNKB
&DeviceSN=owLSOdvg
```

### 响应示例
```
{
    "Action": "GetUIoTCoreGatewayBySubDeviceResponse", 
    "Gateway": {}, 
    "RetCode": 0
}
```

## GetUIoTCoreSubDeviceList

获取子设备列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|网关产品序列号|**Yes**|
|DeviceSN|string|网关设备序列号|**Yes**|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20，最大100|No|
|Status.n|string|子设备状态筛选字段|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总记录数|**Yes**|
|DeviceSet|array|设备列表|**Yes**|

#### SubDeviceData
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DeviceSN|string|设备序列号|**Yes**|
|Password|string|设备密码|**Yes**|
|Status|string|设备状态|**Yes**|
|CreateTime|int|创建时间|**Yes**|
|UpdateStatus|string|设备升级状态|**Yes**|
|ProductName|string|产品名称|**Yes**|
|ProductSN|string|产品序列号|**Yes**|
|ActiveTime|int|设备激活时间|No|
|LatestOnlineTime|int|最近一次上线时间|No|
|LatestOfflineTime|int|最近一次下线时间|No|
|Description|string|设备描述|No|
|FirmwareVersion|string|设备当前固件版本|No|
|DestVersion|string|目标固件版本|No|
|ErrMsg|string|错误信息|No|
|LatestUpdateTime|string|最近一次固件更新时间|No|
|ProductSN|string|所属产品序列号|No|
|DeviceType|string|设备类型|No|
|SubDeviceNum|int|子设备数量|No|
|RemoteSSHOpen|bool|远程SSH开关是否打开|No|
|RemoteSSHPort|int|远程SSH端口|No|
|Driver|object|驱动信息|No|

#### EdgeDriverInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|EdgeDriverID|string|网关驱动ID|**Yes**|
|Config|string|驱动配置|**Yes**|
|IsDeploy|bool|驱动是否部署|**Yes**|
|BindTime|int|驱动绑定时间|**Yes**|
|DriverInfo|object|驱动信息|No|
|ConatinerConfig|string|驱动的容器配置|No|

#### DriverInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DriverID|string|驱动ID|**Yes**|
|DriverName|string|驱动名称|**Yes**|
|Protocol|string|驱动协议|**Yes**|
|Language|string|驱动开发语言|**Yes**|
|MinVersion|string|驱动兼容的网关最小版本|**Yes**|
|DownloadURL|string|驱动下载URL|**Yes**|
|CreateTime|int|驱动创建时间|**Yes**|
|DriverType|string|驱动类型|**Yes**|
|CPUType|string|驱动CPU类型|**Yes**|
|Description|string|驱动描述|No|
|Config|string|驱动配置|No|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreSubDeviceList
&Region=cn-zj
&ProjectId=JWRNAnPs
&ProductSN=peIokvan
&DeviceSN=AlPpkyMc
&Offset=7
&Limit=4
&Status.n=HWAxwlWd
```

### 响应示例
```
{
    "Action": "GetUIoTCoreSubDeviceListResponse", 
    "TotalCount": 5, 
    "RetCode": 0, 
    "DeviceSet": [
        {
            "Status": "oZQtiSIh", 
            "LatestOfflineTime": 5, 
            "ActiveTime": 3, 
            "Description": "CBOUsqzk", 
            "LatestUpdateTime": "FInPyLbL", 
            "DeviceSN": "EzCtqlwg", 
            "CreateTime": 3, 
            "DestVersion": "elgqDeeA", 
            "ErrMsg": "NskYzSfN", 
            "Password": "STBHeLFS", 
            "UpdateStatus": "VXSEtYAz", 
            "FirmwareVersion": "iFDKoWQT", 
            "LatestOnlineTime": 5
        }
    ]
}
```

