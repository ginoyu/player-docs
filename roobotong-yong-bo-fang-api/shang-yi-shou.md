**播放上一首**

服务端根据设备上报的当前状态和播放模式，返回上一首信息，如果指定了下行命令协议，将会调用推送服务，给设备推送ROOBO标准的播放协议

接口： /device/prev

方法： POST

示例： [http://player.roobo.net/device/prev](http://player.roobo.net/device/prev)

请求参数

```
{
  "appId" : "QaNCagiMWCdGbGSj",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "clientId" : "3000020000000020",
  "cmdProtocol" : "mqtt.v1"
}
```

其中参数意义

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必选 | 应用ID |
| token | string | 必选 | 权限TOKEN |
| clientId | string | 必选 | 设备ID |
| userId | string | 可选 | 执行请求的用户ID |
| cmdProtocol | string | 可选 | 是否推送标准播放命令给设备（具体MQTT消息格式参考\*\*） |

返回内容

```
{
    "result":0,
    "msg":"success",
    "data":{
        "resId":"aires:485965",
        "type":1,
        "name":"雨后",
        "favoriteId":"1000",
        "length":259,
        "content" : "http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3",
        "artist":"歌手",
        "album":{
            "id":"100",
            "name":"测试",
            "imgLarge":"http://i.gtimg.cn/music/photo/mid_album_300/X/X/004G5J350sVsXX.jpg",
            "imgSmall":"http://i.gtimg.cn/music/photo/mid_album_300/X/X/004G5J350sVsXX.jpg"
        },
        "playUrls":{
            "normal":{
                "size":4072551,
                "url":"http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3"
            }
        }
    }
}
```

返回内容是上一首资源信息；具体意义参考：[资源详情](/cms/mo-kuai-lie-biao.md)

