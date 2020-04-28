# Python3 SDK使用

本文介绍Python3 SDK的使用，用户可以根据提供的API接口以及子设备的协议编写子设备数据上行及下行逻辑。



## 使用要求

- Python 版本 ≥ Python 3.6.0



## 驱动SDK使用流程

1. 下载Python3 SDK到当前目录（便于打包上传到[驱动管理]()）

   ```bash
    pip3 install uiotedge_driver_link_sdk
   ```

2. 创建`index.py` TODO：根据最后example更新

   ```python
   from uiotedgedriverlinksdk.client import SubDevice, Config
   from uiotedgedriverlinksdk.exception import BaseEdgeException
   import logging
   import time
   import json
   
   # 配置log
   FORMAT = ('%(asctime)-15s %(threadName)-15s '
             '%(levelname)-8s %(module)-15s:%(lineno)-8s %(message)s')
   logging.basicConfig(format=FORMAT)
   log = logging.getLogger()
   log.setLevel(logging.INFO)
   
   # 主函数
   if __name__ == "__main__":
       try:
           # 1. 获取驱动及子设备配置信息
           driverConfig = Config().getDriverInfo()
           deviceInfoList = Config().getDeviceInfos()
       except Exception as e:
           log.error('load driver config error: {}'.format(str(e)))
           exit(1)
   
       try:
           # 判断子设备列表长度不能为0
           if len(deviceInfoList) < 1:
               log.error(
                   'subdevice null, please bind sub device for dirver')
               while True:
                   time.sleep(60)
           # 2. 从子设备列表中获取第一个设备的设备信息及子设备配置               
           subDeviceInfo = deviceInfoList[0]
           productSN = subDeviceInfo['productSN']
           deviceSN = subDeviceInfo['deviceSN']
           deviceConfig = subDeviceInfo['config']
           log.info('sub device config:{}'.format(deviceConfig))
   
           # 定义驱动收到下行消息后的处理逻辑
           def callback(topic: str, payload: b''):
               log.info("recv message from {} : {}".format(topic, str(payload)))
   
           # 3. 创建一个SubDevice对象，注册收到消息后的回调
           #    所有对该设备的操作都是基于该对象，比如子设备的消息上下行、设备上下线
           subDevice = SubDevice(product_sn=productSN,
                                 device_sn=deviceSN, on_msg_callback=callback)
           # 4. 子设备上线
           subDevice.login()
   
           # 5. 上报消息Topic，实际可以通过配置文件指定
           topic = "/{}/{}/upload".format(productSN, deviceSN)
           i = 0
           while True:
               # 获取子设备属性，用户需要根据实际业务定义
               relayStatus = ("on", "off")[i % 2 == 0]
               payload = {
                   "timestamp": time.time(),
                   "relayStatus": relayStatus
               }
               byts = json.dumps(payload).encode('utf-8')
   
               # 上报消息到消息路由
               subDevice.publish(topic, byts)
               log.info("uplaod {} : {}".format(topic, str(byts)))
               time.sleep(5)
               i = i+1
   
       except BaseEdgeException:
           log.error('Edge Exception: {}'.format(str(e)))
       except Exception as e:
           log.error('Exception error: {}'.format(str(e)))
   ```

   

3. 打包驱动

   ```bash
   pip3 install -t . uiotedge_driver_link_sdk  #打包驱动SDK
   pip3 install -t . jsonpath otherpackages #打包自己的依赖
   zip -r driver.zip .
   ```
   
   > 打包需要同时包含所有依赖。

4. 上传驱动zip压缩包到[驱动管理]()

5. [分配驱动]()到网关设备

6. 进行测试

   配置路由后，通过[日志模块]()查看上下行消息内容。



## 驱动API介绍

### uiotedgedriverlinksdk.client包

#### Config()类

创建一个Config对象，用于获取驱动配置、子设备配置。

- **Config.getDeviceInfos() 方法**
- 返回值

| Parameter name | Type | Description  |
| -------------- | ---- | ------------ |
| DeviceInfoList | List | 设备信息列表 |

  - DeviceInfo设备信息

| Parameter name | Type       | Description    |
| -------------- | ---------- | -------------- |
| productSN      | String     | 子产品序列号   |
| deviceSN       | String     | 子设备序列号   |
| config         | Dictionary | 子设备配置信息 |


​    

- **Config.getDriverInfo() 方法**
- 返回值

| Parameter name | Type       | Description  |
| -------------- | ---------- | ------------ |
| DriverInfo     | Dictionary | 驱动配置信息 |




#### SubDevice(product_sn,device_sn, on_msg_callback)类

创建一个SubDevice对象，用于实现对子设备的操作，包括收发消息、设备上下线。

- **SubDevice 构造函数入参**

| Parameter name  | Type     | Description                |
| --------------- | -------- | -------------------------- |
| product_sn      | String   | 子设备产品序列号           |
| device_sn       | String   | 子设备设备序列号           |
| on_msg_callback | Function | 子设备的接收消息的回调函数 |

  - msg_callback: callback(topic:str, msg:b'')
    
    回调函数入参
    
| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| topic     | String | 接收到消息的Topic |
| msg     | b:bytes | 接收到消息的Payload |

- **SubDevice.set_product_sn(product_sn) 方法**

  设置成员变量产品序列号

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| product_sn     | String | 子设备产品序列号 |

- **SubDevice.set_device_sn(device_sn) 方法**

  设置成员变量设备序列号

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| device_sn     | String | 子设备设备序列号 |

- **SubDevice.set_product_secret(product_secret) 方法**

  设置成员变量产品密钥

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| product_secret     | String | 子设备产品密钥 |

- **SubDevice.login(sync=False, timeout=5) 方法**

  子设备上线操作

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| sync     | Bool | 是否异步登录：<br>同步(False)：登录等待云端确认成功reply<br>异步(True)：登录不关心是否云端接收成功 |
| timeout     | Int | 同步时使用，等待超时时间，单位秒 |

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```
    
- **SubDevice.logout(sync=False, timeout=5) 方法**

  子设备下线操作

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| sync     | Bool | 是否异步登出：<br>同步(False)：登出等待云端确认成功reply<br>异步(True)：登出不关心是否云端接收成功 |
| timeout     | Int | 同步时使用，等待超时时间，单位秒 |

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```

- **SubDevice.set_msg_callback(msg_callback) 方法**

  设置收到消息回调函数

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| msg_callback     | Function | 子设备的接收消息的回调函数 |

  - msg_callback: callback(topic:str, msg:b'')
  
    - 回调入参
	
| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| topic     | String | 接收到消息的Topic |
| msg     | b:bytes | 接收到消息的Payload |

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```

- **SubDevice.publish(topic, payload)) 方法**

  发送消息

  - 输入参数
  
| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| topic     | String | 发送消息的Topic |
| payload     | b:bytes | 发送消息的Payload |

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```
  
- **SubDevice.registerDevice(timeout) 方法**

  动态注册子设备，动态注册需要先设置成员变量`product_sn`, `device_sn`, `product_secret`。动态注册原理参考[动态注册](https://docs.ucloud.cn/uiot-core/device_develop_guide/authenticate_devices/unique-certificate-per-product_authentication)。

  - 输入参数
  
| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| timeout     | int | 等待注册成功reply超时时间，单位秒 |

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```

### uiotedgedriverlinksdk.edge包

- **register_device(product_sn, device_sn, product_secret, timeout=5) 函数**

  动态注册子设备，动态注册原理参考[动态注册](https://docs.ucloud.cn/uiot-core/device_develop_guide/authenticate_devices/unique-certificate-per-product_authentication)。

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| product_sn | String | 子设备产品序列号 |
| device_sn | String | 子设备设备序列号 |
| product_secret | String | 子设备设备密钥 |
| timeout     | int | 等待注册成功reply超时时间，单位秒 |

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```

- **set_on_topo_change_callback(callback) 函数**

  设置子设备绑定关系发生改变后的回调函数。

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| callback     | Function | 绑定关系发生改变回调函数 |

  - callback: callback(msg:b'')

    - 回调入参
    
| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| msg     | b:bytes | 绑定关系变化json格式字符串 |

    - msg消息格式
    
    ```json
    {
      "operaction":"add/delete",
      "RequestID": "123",
      "Params": [
        {
          "ProductSN": "product1234",
          "DeviceSN": "device1234",
          "DeviceSecret": "xxxxx"
        }
      ]
    }
    ```

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```

- **set_on_status_change_callback(callback)) 函数**

  设置子设备启用/禁用的回调函数。

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| callback     | Function | 子设备被启用/禁用的回调函数 |

  - callback: callback(msg:b'')

    - 回调入参
    
| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| msg     | b:bytes | 启用/禁用下发的json格式字符串 |

    - msg消息格式
    
    ```json
    {
    	"operaction": "enable/disable",
    	"RequestID": "123",
    	"Params": [{
    			"ProductSN": "product1234",
    			"DeviceSN": "device1234"
    	}]
    }
    ```
  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```
  
- **get_topo(timeout=5)) 函数**

  获取当前网关下的拓扑绑定关系

  - 输入参数
    
    | Parameter name | Type   | Description      |
    | -------------- | ------ | ---------------- |
    | timeout     | int | 等待获取拓扑绑定关系超时时间，单位秒 |
  
  - 返回值
    
| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| topoString     | Json String | 拓扑关系json数据字符串 |

    - Json格式
    
    ```json
    {
        "RequestID": "123",
        "RetCode": 0,
        "Data": [
          {
            "ProductSN": "product1234",
            "DeviceSN": "device1234"
        }
      ]
    }
    ```

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```
  
- **add_topo(product_sn, device_sn, timeout=5) 函数**

  添加拓扑绑定关系

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| product_sn | String | 子设备产品序列号 |
| device_sn | String | 子设备设备序列号 |
| timeout     | int | 等待添加成功reply超时时间，单位秒 |

- 返回Exception
  
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```
  
- **delete_topo(product_sn, device_sn, timeout=5) 函数**

  删除拓扑绑定关系

  - 输入参数

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| product_sn | String | 子设备产品序列号 |
| device_sn | String | 子设备设备序列号 |
| product_secret | String | 子设备设备密钥 |
| timeout     | int | 等待删除成功reply超时时间，单位秒 |

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```
  
- **get_edge_online_status() 函数**

  获取当前边缘网关的在线状态

  - 返回值

| Parameter name | Type   | Description      |
| -------------- | ------ | ---------------- |
| status | Bool | True/False |

  - 返回Exception
    
    异常示例：
    
    ```
    EdgeDriverLinkException:code=1000xx,msg=xxxx
    ```
