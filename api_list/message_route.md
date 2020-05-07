# 设置消息路由


## CreateUIoTCoreMessageRouter

增加消息路由

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|所属网关产品序列号|**Yes**|
|DeviceSN|string|所属网关产品设备序列号|**Yes**|
|SrcType|string|源类型|**Yes**|
|DestType|string|目的类型|**Yes**|
|RouterName|string|消息路由名称|**Yes**|
|FilterTopic|string|过滤主题|**Yes**|
|FilterTopicType|string|过滤主题类型（sys, user, local）|**Yes**|
|Description|string|描述|No|
|SrcID|string|使用的函数计算的名称|No|
|DestID|string|使用的函数计算的名称|No|
|IsCached|string|到云端是否缓存|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreMessageRouter
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=cryegMkE
&RouterName=local
&SrcType=ICtbbHTd
&DestType=FrgsEqYS
&Description=iPpKMIQv
&SrcID=CxZKvnkh
&DestID=SffgdAuY
&IsCached=false
&RouterName=NKgZBvlE
&FilterTopic=kIVZAeiC
&ProductSN=OzfgTzYb
&DeviceSN=ZINRXMVZ
&ProductSN=lJWdLYuW
&DeviceSN=bodaKiSe
&ProductSN=yFMkmYRy
&DeviceSN=BAQaRLOA
&FilterTopicType=wqgeBwPJ
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreMessageRouterResponse", 
    "RetCode": 0
}
```


## DeleteUIoTCoreMessageRouter

删除消息路由

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|消息路由所属网关产品序列号|**Yes**|
|DeviceSN|string|消息路由所属网关产品设备序列号|**Yes**|
|RouterID|string|消息路由ID|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=DeleteUIoTCoreMessageRouter
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=RYplatul
&ProductSN=cfeANkoK
&DeviceSN=QIqghDwV
&RouterID=feQTRXcb
```

### 响应示例
```
{
    "Action": "DeleteUIoTCoreMessageRouterResponse", 
    "RetCode": 0
}
```



## GetUIoTCoreMessageRouterList

获取消息路由列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|所属网关产品序列号|**Yes**|
|DeviceSN|string|所属网关产品设备序列号|**Yes**|
|RouterID|string|消息路由ID|No|
|Offset|int||No|
|Limit|int||No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|RouterSet|array|消息路由集合|No|
|TotalCount|int|消息路由总数|No|

## RouterSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProductSN|string|所属网关产品序列号|**Yes**|
|DeviceSN|string|所属网关设备序列号|**Yes**|
|RouterID|string|消息路由ID|**Yes**|
|RouterName|string|消息路由名称|**Yes**|
|SrcType|string|源类型|**Yes**|
|DestType|string|目的类型|**Yes**|
|FilterTopic|string|过滤主题|**Yes**|
|CreateTime|int|路由创建时间|**Yes**|
|FilterTopicType|string|过滤主题类型（sys,user, local）|**Yes**|
|Description|string|描述|No|
|SrcID|string|使用的函数计算的名称|No|
|DestID|string|使用的函数计算的名称|No|
|IsCached|bool|是否缓存到云端|No|
|DeployTime|int|路由部署时间|No|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreMessageRouterList
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=UzefScex
&ProductSN=sddTsmsZ
&DeviceSN=PwDPuTJL
&RouterID=DjBrNiKH
&Offset=3
&Limit=3
```

### 响应示例
```
{
    "Action": "GetUIoTCoreMessageRouterListResponse", 
    "RouterSet": [
        {
            "RouterName": "tJlcjopo", 
            "Description": "jqmkGVRf", 
            "FilterTopic": "LXFzvAvt", 
            "DestType": "maiHcQUa", 
            "IsCached": true, 
            "CreateTime": 5, 
            "RouterID": "GQbcNKic", 
            "ProductSN": "tZIhDRLE", 
            "DeployTime": 9, 
            "SrcType": "gLyDMUMF", 
            "SrcID": "uGTZvZRR", 
            "DeviceSN": "WqCOGtWk", 
            "DestID": "YEmVaHvi"
        }
    ], 
    "RetCode": 0, 
    "TotalCount": 9
}
```


## ModifyUIoTCoreMessageRouter

修改消息路由

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|所属网关产品序列号|**Yes**|
|DeviceSN|string|所属网关产品设备序列号|**Yes**|
|RouterID|string|消息路由ID|**Yes**|
|RouterName|string|消息路由名称|No|
|Description|string|描述|No|
|SrcType|string|消息路由源类型|No|
|SrcID|string|使用的函数计算的名称|No|
|DestType|string|消息路由目的类型|No|
|DestID|string|使用的函数计算的名称|No|
|IsCached|string|是否缓存到云端|No|
|FilterTopic|string|过滤主题|No|
|FilterTopicType|string|过滤主题类型|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=ModifyUIoTCoreMessageRouter
&Region=cn-zj
&Zone=cn-zj-01
&ProjectId=cByZFlnr
&ProductSN=vNWwILzh
&DeviceSN=BQevbyNU
&RouterID=FBandRCB
&RouterName=nXxSmGoN
&Description=FGDPNWdo
&SrcType=WEHTwZnU
&SrcID=yPMwKHYS
&DestType=beRCfZml
&DestID=RWQZyqFV
&IsCached=QFuNKsBg
&FilterTopic=gKbiwIaf
&FilterTopicType=nhwlheUq
```

### 响应示例
```
{
    "Action": "ModifyUIoTCoreMessageRouterResponse", 
    "RetCode": 0
}
```

