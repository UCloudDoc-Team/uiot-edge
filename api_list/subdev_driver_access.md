# 子设备驱动与接入


## CreateUIoTCoreDriver

创建边缘网关驱动

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DriverName|string|驱动名称|**Yes**|
|Protocol|string|驱动协议|**Yes**|
|Language|string|驱动设计语言|**Yes**|
|MinVersion|string|驱动适配边缘网关最小版本|**Yes**|
|DriverID|string|驱动唯一ID|**Yes**|
|DriverType|string|驱动类型|**Yes**|
|UserCompanyID|int|用户CompanyID|**Yes**|
|UserProjectID|int|用户的ProjectID|**Yes**|
|CPUType|string|驱动CPU类型|No|
|Description|string|驱动描述|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreDriver
&Region=cn-zj
&ProjectId=snCWOKei
&DriverName=ecXKAPJz
&Protocol=DmFcrjPu
&Language=QznerOnE
&MineVersion=XGtjxfsp
&DriverID=jSbedTWi
&DriverType=jVoJttRL
&Description=IxMFdguY
&CPUType=hLUrAljS
&UserCompanyID=2
&UserProjectID=9
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreDriverResponse", 
    "RetCode": 0
}
```



## DeleteUIoTCoreDriver

删除用户的驱动

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DriverID|string|驱动的唯一ID|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=DeleteUIoTCoreDriver
&Region=cn-zj
&ProjectId=HtPNAKmO
&DriverID=LeRSbUxk
```

### 响应示例
```
{
    "Action": "DeleteUIoTCoreDriverResponse", 
    "RetCode": 0
}
```



## ModifyUIoTCoreDriver

修改驱动信息

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DriverID|string|驱动ID|**Yes**|
|MinVersion|string|驱动兼容的最小版本|**Yes**|
|DriverName|string|驱动名称|**Yes**|
|Description|string|驱动描述|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=ModifyUIoTCoreDriver
&Region=cn-zj
&ProjectId=xkKTpldM
&DriverID=ZimXlbYJ
&MineVersion=mJLnChgW
&Description=FjuAVQMb
&DriverName=ZqMOHTMc
```

### 响应示例
```
{
    "Action": "ModifyUIoTCoreDriverResponse", 
    "RetCode": 0
}
```


## GetUIoTCoreDriverInfo

获取驱动信息

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DriverID|string|驱动ID|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DriverInfo|object|驱动信息|**Yes**|

## DriverInfo
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
https://api.ucloud.cn/?Action=GetUIoTCoreDriverInfo
&Region=cn-zj
&ProjectId=zRkyKuIQ
&DriverID=WAkKycwb
```

### 响应示例
```
{
    "DriverInfo": {}, 
    "Action": "GetUIoTCoreDriverInfoResponse", 
    "RetCode": 0
}
```


## GetUIoTCoreDriverList

获取驱动列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DriverName|string|驱动名称|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回最大数据长度，默认为20，最大为100|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DriverList|array|驱动列表|**Yes**|

## Driver
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
https://api.ucloud.cn/?Action=GetUIoTCoreDriverList
&Region=cn-zj
&ProjectId=rYUXPtFX
&DriverName=jtTdLLqH
&Offset=3
&Limit=8
```

### 响应示例
```
{
    "Action": "GetUIoTCoreDriverListResponse", 
    "TotalCount": 9, 
    "DriverList": [
        {
            "DriverType": "iUoWfVJK", 
            "Protocol": "UVqmFgab", 
            "Description": "ZplzEkto", 
            "Language": "KHmqnHvS", 
            "DriverID": "ktBShyam", 
            "MineVersion": "gFVAvdRq", 
            "DownloadURL": "paGGYXrM", 
            "DriverName": "uNExbgIc", 
            "CPUType": "MzPPgoQo", 
            "CreateTime": 2
        }
    ], 
    "RetCode": 0
}
```

## GetUIoTCoreDriverUpdateURL

获取驱动更新上传的URL

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|FileName|string|驱动文件名称|**Yes**|
|MinVersion|string|驱动适配的最小版本|**Yes**|
|MineType|string|驱动上传的ConetextType|**Yes**|
|FileSize|int|驱动文件大小|**Yes**|
|DriverID|string|驱动ID|**Yes**|
|DriverName|string|驱动名称|**Yes**|
|MD5|string|驱动文件的MD5|**Yes**|
|Description|string|驱动描述|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UploadURL|string|驱动上传URL|**Yes**|
|Authorization|string|驱动上传的Authorization|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreDriverUpdateURL
&Region=cn-zj
&ProjectId=RkeSCnyR
&FileName=bQhRvZHH
&MineVersion=VfGgDkHa
&MineType=kBroulcy
&FileSize=dHKsZKfB
&DriverID=qhySMLOj
&Description=lhjKOFcC
&MD5=wtVcxcGC
&DriverID=cuYGFAkF
&DriverName=nXjRuKrS
&DriverName=bdTCRvyS
```

### 响应示例
```
{
    "Action": "GetUIoTCoreDriverUpdateURLResponse", 
    "RetCode": 0, 
    "Authorization": "keUhDFSM", 
    "UploadURL": "SDylObDj"
}
```


## GetUIoTCoreDriverUploadURL

获取驱动上传URL

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DriverName|string|驱动名称|**Yes**|
|DriverType|string|驱动类型|**Yes**|
|Protocol|string|驱动协议|**Yes**|
|Language|string|驱动开发语言|**Yes**|
|FileName|string|驱动文件名称|**Yes**|
|MD5|string|驱动文件的MD5|**Yes**|
|FileSize|int|驱动文件大小|**Yes**|
|MinVersion|string|驱动适用边缘网关的最小版本|**Yes**|
|MineType|string|驱动文件上传的contextType|**Yes**|
|CPUType|string|驱动使用的CPU架构|No|
|Description|string|驱动描述|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|UploadURL|string|驱动上传URL|No|
|Authorization|string|驱动上传的Authorization|No|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreDriverUploadURL
&Region=cn-zj
&ProjectId=wjlIVckS
&DriverName=JHLEPatE
&DriverType=ojVMxJCK
&Protocol=VAIgkNRV
&Language=uHKVfidU
&MineVersion=XfjpRzAN
&CPUType=HDLjRfJv
&FileName=TjSOzFfm
&Description=SNKDamnX
&MineType=AgBOcStF
&MD5=GhHeeqZd
&FileSize=5
```

### 响应示例
```
{
    "Action": "GetUIoTCoreDriverUploadURLResponse", 
    "RetCode": 0, 
    "Authorization": "ieIJgsFY", 
    "UploadURL": "dRPNihvg"
}
```

## CreateUIoTCoreEdgeDriverBind

网关绑定驱动

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|网关设备ProductSN|**Yes**|
|DeviceSN|string|网关设备	DeviceSN  |**Yes**|
|DriverID|string|驱动ID|**Yes**|
|Config|string|驱动配置|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreEdgeDriverBind
&Region=cn-zj
&ProjectId=FcIckrJd
&ProductSN=SErGMBcY
&DeviceSN=HwipARsb
&DriverID=YRhZKuJQ
&Config=TfkDoFZp
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreEdgeDriverBindResponse", 
    "RetCode": 0
}
```

## CreateUIoTCoreMultiDriverBind

批量绑定网关和驱动

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|ProductSN|**Yes**|
|DeviceSN|string|DeviceSN|**Yes**|
|DriverID.n|string|驱动ID列表|**Yes**|
|Config|string|驱动配置|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|FailedList|array|错误列表|**Yes**|

## Failed
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DriverID|string|驱动ID|**Yes**|
|Reason|string|错误原因|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreMultiDriverBind
&Region=cn-zj
&ProjectId=lRRrjvfe
&ProductSN=hQhWxoYe
&DeviceSN=CaBaJXGk
&DriverID.n=FGXZRIlc
&Config=otWaeGpZ
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreMultiDriverBindResponse", 
    "FailedList": [
        {
            "DriverID": "TSXKrbMd", 
            "Reason": "RTiZjuXj"
        }
    ], 
    "RetCode": 0
}
```

## GetUIoTCoreEdgeDriverList

获取网关绑定驱动列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|网关设备ProductSN|**Yes**|
|DeviceSN|string|网关设备DeviceSN|**Yes**|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回最大数据长度，默认为20，最大为100|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|EdgeDriverList|array|驱动列表|**Yes**|

## EdgeDriver
|Parameter name|Type|Description|Required|
|---|---|---|---|
|EdgeDriverID|string|网关驱动ID|**Yes**|
|Config|string|驱动配置|**Yes**|
|IsDeploy|bool|驱动是否部署|**Yes**|
|BindTime|int|驱动绑定时间|**Yes**|
|DriverInfo|object|驱动信息|No|
|ConatinerConfig|string|驱动的容器配置|No|

## DriverInfo
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
https://api.ucloud.cn/?Action=GetUIoTCoreEdgeDriverList
&Region=cn-zj
&ProjectId=gBIHsjnJ
&ProductSN=cbZUVfrC
&DeviceSN=TFaJgpzA
&Offset=3
&Limit=2
```

### 响应示例
```
{
    "Action": "GetUIoTCoreEdgeDriverListResponse", 
    "TotalCount": 3, 
    "DriverList": [
        {
            "DriverType": "oPQPsBEj", 
            "Protocol": "IgeGsXFn", 
            "Description": "MkJXfkJp", 
            "Language": "xmheRqFb", 
            "DriverID": "furkBxQl", 
            "MineVersion": "BJRQjbKu", 
            "DownloadURL": "bJCShQjK", 
            "DriverName": "BgSzlHke", 
            "CPUType": "GZrevXNN", 
            "CreateTime": 2
        }
    ], 
    "RetCode": 0
}
```

## DeleteUIoTCoreEdgeDriverBind

删除网关和驱动绑定

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|EdgeDriverID|string|网关驱动ID|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=DeleteUIoTCoreEdgeDriverBind
&Region=cn-zj
&ProjectId=jGwFvEBJ
&ProductSN=JFwQkjOE
&DeviceSN=TSwdjlbM
&DriverID=meyrrfWD
```

### 响应示例
```
{
    "Action": "DeleteUIoTCoreEdgeDriverBindResponse", 
    "RetCode": 0
}
```

## GetUIoTCoreBindableProductList

获取可绑定产品列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|网关产品序列号|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ProductSet|array|可绑定设备列表|**Yes**|

## ProductSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProductSN|string|产品序列号|**Yes**|
|ProductName|string|产品名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreBindableProductList
&Region=cn-zj
&ProjectId=xQrKEpMc
&ProductSN=NruZQdvR
&DeviceSN=NGZhLYNX
```

### 响应示例
```
{
    "Action": "GetUIoTCoreBindableProductListResponse", 
    "BindableProductList": [
        "bmhqUZQh"
    ], 
    "RetCode": 0
}
```


## GetUIoTCoreBindableDeviceList

获取可绑定设备列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|产品序列号|**Yes**|
|DeviceSN|string|设备序列号|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20，最大100|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|TotalCount|int|总记录数|**Yes**|
|DeviceSet|array|设备列表|**Yes**|

## DeviceSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DeviceSN|string|设备序列号|**Yes**|
|Description|string|设备描述|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreBindableDeviceList
&Region=cn-zj
&ProjectId=LjOecSDk
&ProductSN=ZSbtEmLr
&Offset=4
&Limit=2
&DeviceSN=pYqfmmRb
```

### 响应示例
```
{
    "Action": "GetUIoTCoreBindableDeviceListResponse", 
    "TotalCount": 2, 
    "RetCode": 0, 
    "DeviceSet": [
        "qfSYgxhh"
    ]
}
```

## CreateUIoTCoreDriverSubDevBind

驱动绑定子设备

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|子设备ProductSN|**Yes**|
|DeviceSN|string|子设备DeviceSN|**Yes**|
|EdgeDriverID|string|网关驱动ID|**Yes**|
|Config|string|子设备配置|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreDriverSubDevBind
&Region=cn-zj
&ProjectId=ZDDNMvbw
&ProductSN=HkGCgLVs
&DeviceSN=ZFwKJSVH
&EdgeDriverID=LXfloNWF
&Config=JWfoxoIx
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreDriverSubDevBindResponse", 
    "RetCode": 0
}
```


## CreateUIoTCoreMultiSubDevBind

批量创建驱动和子设备绑定

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|DeviceInfo.n|string|设备信息。内容为: productSN空格deviceSN|**Yes**|
|EdgeDriverID|string|网关驱动ID|**Yes**|
|Config|string|子设备配置|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|FailedList|array|错误设备列表|No|

## Failed
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProductSN|string|设备productsn|**Yes**|
|DeviceSN|string|DeviceSN|**Yes**|
|Reason|string|错误原因|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=CreateUIoTCoreMultiSubDevBind
&Region=cn-zj
&ProjectId=PbKBvVLo
&DeviceInfo.n=kqesLdaY
&EdgeDriverID=eTcAfxWV
&Config=qAENJvAZ
```

### 响应示例
```
{
    "Action": "CreateUIoTCoreMultiSubDevBindResponse", 
    "FailedList": [
        {
            "Reason": "iZQVWDrk", 
            "ProductSN": "URvXJrtJ", 
            "DeviceSN": "mFWwcoXB"
        }
    ], 
    "RetCode": 0
}
```

## GetUIoTCoreDriverSubDevList

获取驱动子设备列表

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|EdgeDriverID|string|网关的驱动ID|**Yes**|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回最大数据长度，默认为20，最大为100|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SubDeviceList|array|设备列表|**Yes**|

## SubDevice
|Parameter name|Type|Description|Required|
|---|---|---|---|
|DeviceInfo|object||**Yes**|
|EdgeDriverID|string|网关驱动ID|No|
|Config|string|子设备配置|No|

## DeviceInfo
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

### 请求示例
```
https://api.ucloud.cn/?Action=GetUIoTCoreDriverSubDevList
&Region=cn-zj
&ProjectId=ZlWxZIaH
&EdgeDriverID=SbgJjnEW
&Offset=1
&Limit=8
```

### 响应示例
```
{
    "DeviceList": [
        {
            "Status": "eZvopfGc", 
            "LatestOfflineTime": 2, 
            "ActiveTime": 6, 
            "SubDeviceNum": 8, 
            "Description": "hvvsmOJg", 
            "LatestUpdateTime": "tbvPhbKA", 
            "DeviceSN": "JbcSmXQs", 
            "ProductSN": "TmmGesNy", 
            "CreateTime": 7, 
            "DestVersion": "DEnbkXYX", 
            "DeviceType": "fmmOlnLw", 
            "ErrMsg": "gYChLCbo", 
            "Password": "qwyNRPZH", 
            "UpdateStatus": "JaybSVMr", 
            "FirmwareVersion": "KghNmzIe", 
            "LatestOnlineTime": 9
        }
    ], 
    "Action": "GetUIoTCoreDriverSubDevListResponse", 
    "RetCode": 0, 
    "TotalCount": 8
}
```

## DeleteUIoTCoreDriverSubBind

删除驱动和子设备绑定

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|子设备ProductSN|**Yes**|
|DeviceSN|string|子设备DeviceSN|**Yes**|
|EdgeDriverID|string|网关驱动ID|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=DeleteUIoTCoreDriverSubBind
&Region=cn-zj
&ProjectId=ROKbCbEs
&ProductSN=vudIPwao
&DeviceSN=zervotDn
&EdgeDriverID=RsmNQFZe
```

### 响应示例
```
{
    "Action": "DeleteUIoTCoreDriverSubBindResponse", 
    "RetCode": 0
}
```


## ModifyUIoTCoreEdgeDriverConf

修改网关驱动配置

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|EdgeDriverID|string|网关驱动ID|**Yes**|
|Config|string|网关驱动配置|**Yes**|
|IsContainer|bool|是否是修改驱动容器配置，默认false，为修改驱动配置，true为修改驱动的容器配置|No|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=ModifyUIoTCoreEdgeDriverConf
&Region=cn-zj
&ProjectId=BKPkMpsk
&EdgeDriverID=oJreonwG
&Config=mxZpCAfs
&IsContainer=true
```

### 响应示例
```
{
    "Action": "ModifyUIoTCoreEdgeDriverConfResponse", 
    "RetCode": 0
}
```

## ModifyUIoTCoreDriverSubDevConf

修改驱动的子设备配置

### 请求参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
| Region         | string | 地域。 参见 [地域和可用区列表](https://docs.ucloud.cn/api/summary/regionlist)  |  **Yes** |
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ProductSN|string|子设备ProductSN|**Yes**|
|DeviceSN|string|子设备DeviceSN|**Yes**|
|EdgeDriverID|string|网关驱动ID|**Yes**|
|Config|string|子设备配置|**Yes**|

### 响应参数
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

### 请求示例
```
https://api.ucloud.cn/?Action=ModifyUIoTCoreDriverSubDevConf
&Region=cn-zj
&ProjectId=RDUIXMCO
&ProductSN=QYDMlNmP
&DeviceSN=XJDZBtWg
&EdgeDriverID=RvVlGDrM
&Config=rFrYizCs
```

### 响应示例
```
{
    "Action": "ModifyUIoTCoreDriverSubDevConfResponse", 
    "RetCode": 0
}
```


