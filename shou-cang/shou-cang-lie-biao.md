**获取收藏列表**

接口： /favorite/list

方法： POST

示例：[http://player.roobo.net/favorites/list](http://player.roobo.net/favorites/list)

请求参数

```
{
    "appId" : "QaNCagiMWCdGbGSj",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "userId":"ps:5724e37aa1bfd42510b52256ec620b17",
    "clientId":"1011000000101005",
    "ranges" : [ "resource", "album" ],
    "count" : 20,
    "page" : 1
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string |  | 应用ID |
| userId | string | 是 | 过滤指定用户ID收藏的 |
| clientId | string |  | 设备ID |
| ranges | string | 是 | 查询范围： resource代表查询资源收藏；album查询专辑收藏默认代表只查询资源收藏 |
| page | int | 是 | 分页页面，默认为1 |
| count | int | 是 | 每页数量，默认为20 |

返回值

```
{
  "result": 0,
  "msg": "success",
  "data": {
    "production": "pudding1s",
    "clientId": "1011000000101005",
    "resources": [
      {
        "favoriteId": "47",
        "userId": "ps:5724e37aa1bfd42510b52256ec620b17",
        "time": 1478246159,
        "resId": "aires:486237",
        "type": 1,
        "name": "登幽州台歌",
        "content": "http://dwn.roo.bo/voices/songs/koudai/c1732e988e6fc2fc5aebd54c6c9a30b9.mp3",
        "length": 103,
        "artist": "陈子昂",
        "album": {
            "id": "11543",
            "name": "古诗古词",
            "imgLarge": "http://media.roo.bo//thirdparty/20170816/4acef775e7730c27ca3a92ca7167e7e6.png",
            "imgSmall": "http://media.roo.bo//thirdparty/20170816/af47b76306a1f4813d8fc5f43680036c.png"
        },
        "playUrls": {
            "normal": {
                "size": 0,
                "url": "http://dwn.roo.bo/voices/songs/koudai/c1732e988e6fc2fc5aebd54c6c9a30b9.mp3"
            }
        }
      }
    ],
    "albums" : [
      {
        "favoriteId": "47",
        "userId": "ps:5724e37aa1bfd42510b52256ec620b17",
        "time": 1478246159,
        "albumbId" : "1000",
        "name" : "歌单标题",
        "total" : 10,
        "type":"album",
        "imgLarge" : "http://media.roobo.net/appimg/20161114_67fe4ba23ba80b325d4b388838d31853.png",
        "imgSmall" : "http://media.roobo.net/appimg/20161117_fea417c257b8b2826f801d41a3a48931.jpg"
      }
    ]
  }
}
```

其中

| 参数 | 返回值 | 意义 |
| :--- | :--- | :--- |
| data.resources\[\].favoriteId | string | 收藏记录ID |
| data.resources\[\].resId | string | 资源ID |
| data.production | string | 设备产品线 |
| data.clientId | string | 播放主体ID |
| data.resources\[\].userId | string | 执行收藏的用户ID |
| data.resources\[\].type | int | 资源类型 |
| data.resources\[\].name | string | 资源名称 |
| data.resources\[\].content | string | 资源播放连接 |
| data.resources\[\].length | int | 资源长度（因为资源文件的变更，可能和实际资源长度不一致，这里只用于和currentLength判定代表是否播放完成） |
| data.resources\[\].artist | string | 资源作者 |
| data.resources\[\].album | object | 资源专辑信息 |
| data.resources\[\].playUrls | object | 资源播放连接 |
| data.resources\[\].time | int | 收藏时间（UNIX时间戳） |
| data.albums\[\].favoriteId | string | 收藏记录ID |
| data.albums\[\].userId | string | 执行收藏的用户ID |
| data.albums\[\].time | int | 收藏时间（UNIX时间戳） |
| data.albums\[\].albumId | string | 歌单ID |
| data.albums\[\].name | string | 歌单名称 |
| data.albums\[\].total | int | 歌单下资源数 |
| data.albums\[\].type | string | 歌单类型 |
| data.albums\[\].imgLarge | string | 歌单大图 |
| data.albums\[\].imgSmall | string | 歌单小图 |



