---
created: 2024-12-22T20:54:18 (UTC +08:00)
tags: []
source: https://github.com/md-frank/file-service/wiki/image-sizes.json%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E8%AF%B4%E6%98%8E
author: 
---

# image sizes.json配置文件说明 · md-frank/file-service Wiki

> 下载128x128大小的缩略图（原文件是图像）
文件根地址/image/128x128，例如： http://file.domain.com/files/1iYQTU7fEUgaa~URSVwaCqQKFml_IAAAAAgAAAAbhmsFjiUUQwCPn2ngI1QcvsSp0AA/image/128x128

以这个为例，客户端能拼接什么尺寸的图片大小是在这个配置文件里指定的，其中128x128就对应了配置文件中的Name字段

```json
{
  "ImageSizes": [
    {
      //图片大小名称
      "Name": "32x32",
      //宽（像素）
      "Width": 32,
      //高（像素）
      "Height": 32
    },
    {
      "Name": "64x64",
      "Width": 64,
      "Height": 64
    },
    {
      "Name": "128x128",
      "Width": 128,
      "Height": 128
    },
    {
      "Name": "256x",
      "Width": 256,
      //高（像素），如果为0表示等比例缩放
      "Height": 0
    },
    {
      "Name": "450x",
      "Width": 450,
      "Height": 0
    }    
  ]
}
```
