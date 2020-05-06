# 添加函数计算


## CreateUIoTCoreFunction

创建函数

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FunctionName|string|创建的函数名称，函数名称支持26个英文字母大小写、数字、连接符和下划线，第一个字符只能以字母开头，最后一个字符不能为连接符或者下划线，名称长度2-31|**Yes**|
|Handler|string|函数处理方法名称，名称格式支持 "文件名称.方法名称" 形式，文件名称和函数名称之间以"."隔开，文件名称和函数名称要求以字母开始和结尾，中间允许插入字母、数字、下划线和连接符，文件名称和函数名字的长度要求是 2-31 个字符。默认index.handler|No|
|Runtime|string|运行环境，目前支持Python3.6，默认"python36"|No|
|Code|string|函数的代码。目前为base64(file)|No|
|Description|string|描述|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreFunction
&Region=cn-zj
&ProjectId=qJpWGvIJ
&FunctionName=cubrnney
&Handler=vBPWjynl
&Runtime=iXGCFAzx
&Code=TYjwbhmr
&Description=GjdmyVWk
&CodeSource=sTLTVJFs
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreFunctionResponse", 
    "RetCode": 0
}
```


## DeleteUIoTCoreFunction

删除函数

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FunctionName|string|函数名称|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=DeleteUIoTCoreFunction
&Region=cn-zj
&ProjectId=ikzWBLaW
&FunctionName=KRNRXdSs
```

### 响应示例
```
{
    "Action": "DeleteUIoTCoreFunctionResponse", 
    "RetCode": 0
}
```



## UpdateUIoTCoreFunction

更新函数

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FunctionName|string|要修改的函数名称|**Yes**|
|Runtime|string|要修改的运行环境，为空不修改|No|
|Handler|string|要修改的函数入口，为空不修改|No|
|Description|string|要修改的函数描述，注意为空会删除原有描述|No|
|Code|string|要修改的函数代码，为空不修改|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=UpdateUIoTCoreFunction
&Region=cn-zj
&ProjectId=JExPuCiU
&FunctionName=qMVKsrLu
&Runtime=DiZFNGSa
&Handler=XxPnwIDN
&Description=kvnGiwhu
&Code=XtHqEXpq
```

### 响应示例
```
{
    "Action": "UpdateUIoTCoreFunctionResponse", 
    "RetCode": 0
}
```


## GetUIoTCoreFunctionList

获取函数列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FunctionName|string|支持FunctionName模糊匹配|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20，最大100|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总数|**Yes**|
|Functions|array|函数列表|**Yes**|

## Function
|Parameter name|Type|Description|Required|
|---|---|---|---|
|FunctionName|string|函数名|No|
|Runtime|string|运行环境|No|
|CreateTime|int|创建时间|No|
|LastModifiedTime|int|最近修改时间|No|
|CodeChecksum|string|代码校验和|No|
|CodeSize|int|代码包大小|No|
|CodeURL|string|代码包下载地址|No|
|Handler|string|函数入口|No|
|Description|string|函数描述|No|
|FunctionId|string|函数ID|No|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreFunctionList
&Region=cn-zj
&ProjectId=yOjVOXuF
&FunctionName=cdDjrTVD
&Offset=6
&Limit=6
```

### 响应示例
```
{
    "Action": "GetUIoTCoreFunctionListResponse", 
    "TotalCount": 5, 
    "Functions": [
        "LlEiiDtk"
    ], 
    "RetCode": 0
}
```


## BindUIoTCoreFunctionToEdge

绑定函数至边缘网关

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FunctionName|string|函数名|**Yes**|
|ProductSN|string|边缘网关产品序列号|**Yes**|
|DeviceSN|string|边缘网关设备序列号|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=BindUIoTCoreFunctionToEdge
&Region=cn-zj
&ProjectId=adNKKkJU
&FunctionName=SciPvfAv
&ProductSN=QuyizSpW
&DeviceSN=NYUGuWKC
```

### 响应示例
```
{
    "Action": "BindUIoTCoreFunctionToEdgeResponse", 
    "RetCode": 0
}
```


## GetUIoTCoreEdgeFunctionList

获取边缘网关函数列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|边缘网关产品序列号|**Yes**|
|DeviceSN|string|边缘网关设备序列号|**Yes**|
|FunctionName|string|函数名筛选字段|No|
|Offset|string|默认0|No|
|Limit|string|默认20|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|Functions|array|函数列表|**Yes**|
|TotalCount|int|总数|No|

## Function
|Parameter name|Type|Description|Required|
|---|---|---|---|
|FunctionName|string|函数名|No|
|Runtime|string|运行环境|No|
|CreateTime|int|创建时间|No|
|LastModifiedTime|int|最近修改时间|No|
|CodeChecksum|string|代码校验和|No|
|CodeSize|int|代码包大小|No|
|CodeURL|string|代码包下载地址|No|
|Handler|string|函数入口|No|
|Description|string|函数描述|No|
|FunctionId|string|函数ID|No|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreEdgeFunctionList
&Region=cn-zj
&ProjectId=VFLckUcy
&ProductSN=oDxnzVaC
&DeviceSN=FjXZZRhn
&Offset=6
&Limit=5
&FunctionName=JuUkmScj
&Offset=fpqkBheR
&Limit=HLHcmQMa
```

### 响应示例
```
{
    "Action": "GetUIoTCoreEdgeFunctionListResponse", 
    "TotalCount": 6, 
    "Functions": [
        {
            "FunctionName": "uIPFAfSK", 
            "CodeChecksum": "uYOQlpYq", 
            "CodeSize": 4, 
            "Handler": "kVuftBBZ", 
            "CreatedTime": 7, 
            "LastModifiedTime": 1, 
            "Runtime": "lktwKivm", 
            "FunctionId": "RyxnrRPF", 
            "Description": "qwYsPivO"
        }
    ], 
    "RetCode": 0
}
```


## UnBindUIoTCoreFunctionFromEdge

将函数从边缘网关解绑

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FunctionName|string|函数名|**Yes**|
|ProductSN|string|边缘网关产品序列号|**Yes**|
|DeviceSN|string|边缘网关设备序列号|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=UnBindUIoTCoreFunctionFromEdge
&Region=cn-zj
&ProjectId=LymPzJcD
&FunctionName=PKwCUwMV
&ProductSN=fHQVGSuo
&DeviceSN=OSxBDvOy
```

### 响应示例
```
{
    "Action": "UnBindUIoTCoreFunctionFromEdgeResponse", 
    "RetCode": 0
}
```

