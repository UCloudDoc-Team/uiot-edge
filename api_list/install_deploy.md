# 安装及部署


## CreateUIoTCoreEdgeDeployment

创建边缘部署任务

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|边缘网关产品序列号|**Yes**|
|DeviceSN|string|边缘网关设备序列号|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DeploymentID|string|部署ID|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreEdgeDeployment
&Region=cn-zj
&ProjectId=keuKXirU
&ProductSN=URhTqvZP
&DeviceSN=aRKFHwnK
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreEdgeDeploymentResponse", 
    "DeploymentID": "YhxflGDH", 
    "RetCode": 0
}
```



## CreateUIoTCoreReinstall

重装软件

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|网关产品序列号|**Yes**|
|DeviceSN|string|网关设备序列号|**Yes**|
|CPUArch|string|网关CPU架构,支持x86-64 和 arm7|**Yes**|
|SoftwareVersion|string|安装软件版本 |**Yes**|
|OS|string|网关操作系统 支持linux，windows，mac|**Yes**|
|Mode|string|运行模式，默认为native, 支持 docker和native|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Info|object|重装参数|**Yes**|

## ReinstallInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CPUArch|string|网关CPU架构|No|
|Version|string|安装软件版本|No|
|OS|string|网关操作系统|No|
|RAM|string|运行所需内存|No|
|Memory|string|安装所需内存|No|
|DownloadCmd|string|下载命令|No|
|Mode|string|运行模式|No|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreReinstall
&Region=cn-zj
&ProjectId=Ozjpjvdg
&ProductSN=DAqSumVQ
&DeviceSN=jpqtsifG
&CPUArch=XCFxzPPQ
&Version=LwlsfpTM
&OS=RSJylGvV
&Mode=wjyyzbUa
&Mode=HRPdkYQv
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreReinstallResponse", 
    "Data": {}, 
    "RetCode": 0
}
```


## GetUIoTCoreReinstallInfo

获取设备网关安装信息

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|ProductSN|**Yes**|
|DeviceSN|string|DeviceSN|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Info|object|网关安装信息|**Yes**|

## ReinstallInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CPUArch|string|网关CPU架构|No|
|Version|string|安装软件版本|No|
|OS|string|网关操作系统|No|
|RAM|string|运行所需内存|No|
|Memory|string|安装所需内存|No|
|DownloadCmd|string|下载命令|No|
|Mode|string|运行模式|No|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreReinstallInfo
&Region=cn-zj
&ProjectId=cVWAIDam
&ProductSN=agbtuLuN
&DeviceSN=aMJMpXGn
```

### 响应示例
```
{
    "Action": "GetUIoTCoreReinstallInfoResponse", 
    "Data": {}, 
    "RetCode": 0
}
```


## GetUIoTCoreEdgeDeploymentList

获取边缘部署任务列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|边缘网关产品序列号|**Yes**|
|DeviceSN|string|边缘网关设备序列号|**Yes**|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20，最大100|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总记录数|**Yes**|
|Deployments|array|部署任务列表|**Yes**|

## Deployment
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DeploymentID|string|部署ID|No|
|Status|string|部署状态，共有"init", "processing", "success", "failure", "timeout"五种状态|No|
|CreateTime|int|部署任务创建时间|No|
|LastModifiedTime|int|部署任务最后修改时间|No|
|Log|string|部署任务日志|No|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreEdgeDeploymentList
&Region=cn-zj
&ProjectId=arkHTPEo
&ProductSN=TsYzKIAk
&DeviceSN=XLLUViIF
&Offset=6
&Limit=8
```

### 响应示例
```
{
    "Action": "GetUIoTCoreEdgeDeploymentListResponse", 
    "TotalCount": 1, 
    "RetCode": 0, 
    "Deployments": [
        "bKTsUnuL"
    ]
}
```


## GetUIoTCoreEdgeDeploymentInfo

获取边缘部署任务信息

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DeploymentID|string|部署ID|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DeploymentInfo|object|部署信息|**Yes**|

## Deployment
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DeploymentID|string|部署ID|No|
|Status|string|部署状态，共有"init", "processing", "success", "failure", "timeout"五种状态|No|
|CreateTime|int|部署任务创建时间|No|
|LastModifiedTime|int|部署任务最后修改时间|No|
|Log|string|部署任务日志|No|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreEdgeDeploymentInfo
&Region=cn-zj
&ProjectId=tBwdDVtr
&DeploymentID=JCYPyXQn
```

### 响应示例
```
{
    "Action": "GetUIoTCoreEdgeDeploymentInfoResponse", 
    "RetCode": 0, 
    "DeploymentInfo": {}
}
```

## GetUIoTCoreLatestEdgeDeploy

GetUIoTCoreLatestEdgeDeploy

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string||**Yes**|
|DeviceSN|string||**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DeployInfo|object||**Yes**|

## DeploySet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProductSN|string|网关设备产品序列号|**Yes**|
|DeviceSN|string|网关设备设备序列号|**Yes**|
|DeployID|string|部署ID|**Yes**|
|DeployTime|int|部署时间|**Yes**|
|DeployStatus|string|部署状态|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreLatestEdgeDeploy
&Region=cn-zj
&ProjectId=tvYQhpwX
&ProductSN=UzbdxUDj
&DeviceSN=pftsVnGQ
```

### 响应示例
```
{
    "Action": "GetUIoTCoreLatestEdgeDeployResponse", 
    "Set": [
        {
            "DeployStatus": "JVGpGyyQ", 
            "DeployID": "KREPVtpl", 
            "ProductSN": "XCkQkLdr", 
            "DeployTime": 8, 
            "DeviceSN": "EBdUquhU"
        }
    ], 
    "RetCode": 0, 
    "DeployInfo": {}
}
```
