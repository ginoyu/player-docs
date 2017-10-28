**获取播放状态**

接口： /status/get

方法： POST

示例： [http://player.roobo.net/status/get](http://player.roobo.net/status/get)

请求参数:

```
{
    "appId":"EvXLUN3xtyON74KY",
    "clientId":"10110000002003C7",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
    "skipStop" : true
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| clientId | string | 必填 | 客户端ID（用户ID或者设备ID） |
| token | string | 必填 | 设备TOKEN或者appId token |
| userId | string | 可选 | 当前查询的用户ID，用于检查收藏 |
| skipStop | string | 可选 | 是否过滤状态为stop的记录；如果当前播放状态为stop，且skipStop为true，返回数据为空；否则返回stop状态数据 |

返回示例:

```
{
    "result":0,
    "msg":"success",
    "data": {
        "resource": {
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
        },
        "status":"ready",
        "offset":0,
        "trigger" : "album",
        "timestamp":1478866368,
        "playmode" : "random"
    }
}
```

返回值意义

| 返回值 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.resource | object | 当前正在播放的资源（参考） |
| data.status | string | 当前播放状态：ready 准备播放-初始值；  loading 播放加载中；  play 播放中；  pause 暂停； stop 结束 |
| data.offset | int | 设备最后一次上报的播放进度结合data.timestamp可用来计算当前设备的播放进度 |
| data.trigger | string | 当前播放触发的方式album 歌单播放 |
| data.timestamp | int | 设备上报offset的时间戳（UNIX时间戳） |
| data.playmode | string | 当前播放模式，参考： |



