# python3 SDK使用

本文介绍python SDK的使用，用户可以根据提供的API接口以及子设备的协议编写子设备数据上行及下行逻辑。



## 使用要求

- python 版本 ≥ python 3.6.0



## 驱动SDK使用流程

1. 下载python3 SDK到当前目录（便于打包上传到[驱动管理]()）

   ```bash
    pip3 install uiotedge_driver_link_sdk
   ```

2. 创建`index.py`

   ```python
   
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