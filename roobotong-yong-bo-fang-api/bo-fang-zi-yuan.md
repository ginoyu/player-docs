**播放指定的资源**

接口： /play

方法： POST

示例： [http://player.roobo.net/play](http://player.roobo.net/play)

请求参数

```
{
  "appId" : "QaNCagiMWCdGbGSj",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId":"3000020000000020",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "resId":"aires:485965",
  "albumId" : "100",
  "trigger" : "album",
  "cmdProtocol" : "mqtt.v1"
}
```

其中请求参数意义

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | 产品TOKEN |
| clientId | string | 必填 | 播放设备ID |
| userId | string | 可选 | 执行播放操作的用户ID |
| resId | string | 必填 | 需要播放的资源ID |
| albumId | string | 可选 | 该资源关联的歌单ID，用于上一首，下一首时根据歌单ID自动进行 |
| trigger | string | 可选 | 点播方式（默认值album）：album-歌单点播；history-历史记录点播；favorite-收藏点播 |
| cmdProtocol | string | 可选 | 是否推送标准播放命令给设备（具体MQTT消息格式参考\*\*） |

返回值

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

返回内容是当前播放的资源信息；具体意义参考：[资源详情](/cms/mo-kuai-lie-biao.md)

