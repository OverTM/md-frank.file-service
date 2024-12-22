---
created: 2024-12-22T20:52:17 (UTC +08:00)
tags: []
source: https://github.com/md-frank/file-service/wiki/appsettings.json%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E8%AF%B4%E6%98%8E
author: 
---

# appsettings.json配置文件说明 · md-frank/file-service Wiki
 

```json
{
  "Logging": {
    "IncludeScopes": false,
    "LogLevel": {
      "Default": "Debug",
      "System": "Information",
      "Microsoft": "Information"
    },
    //日志文件目录
    "LogsDir": "/var/log/Mondol.FileService"
  },
  "Server": {
    //当前是否使用了反向代理，例如：nginx
    "ReverseProxy": true
  },
  "Db": {
    //1 - MySQL | 2 - MSSQL
    "DbType": 1,
    "MasterConnectionString": "server=127.0.0.1;user id=xxx;password=xxx;database=file-service; pooling=true;",
    //分表数量，无特殊需求保持64
    "FileTableCount": 64
  },
  "General": {
    //上传的文件存储根目录
    "RootPath": "/data/Mondol.FileService/files",
    //加密密钥，与业务服务器相同
    "AppSecret": "xxxxxxxxxxxxxxx",
    //下载文件时是否查询文件名。true:从属性库查询文件名返回给客户端 | false: 不查询数据库，性能好
    "QueryFileName": false
  },
  //图片处理器转换参数，参考imagemagick
  "ImageConverter": {
    "ConverterPath": "convert",
    "ResizeArgs": "${width}x${height}&gt;",
    "ConvertTimeout": 60
  },
  "Manage": {
    //业务服务器IP白名单，只有在白名单里的IP才能管理文件服务器
    "IpWhitelist": [
      "*"
    ]
  },
  //集群配置
  "Cluster": {
    //当前服务器的ID
    "SelfServerId": 1,
    "Servers": [
      {
        //服务器ID，唯一
        "Id": 1,
        //服务器域名或IP，例如：fs.domain.com
        "Host": "127.0.0.1:5001",
        //权重，权重大的服务器会优先上传文件
        "Weight": 1,
        //本台服务器是否允许上传
        "AllowUpload": true
      }
    ]
  }
}
```
