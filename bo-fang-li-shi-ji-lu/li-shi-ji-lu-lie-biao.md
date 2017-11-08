**查询播放历史记录**

查询指定播放主体（设备）的播放历史记录， 相同的资源只会合并返回最近的一条历史记录

接口：/playrecord/list

方法：POST

示例： [http://player.roobo.net/playrecord/list](http://player.roobo.net/playrecord/list)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "clientId" : "1015000000101064",
  "token":"786203ce01256d1d590e2d0a1c1f11b62076",
  "from" : "0",
  "size" : 20,
  "resDB" : ["aires"],
  "order" : "desc"
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | 设备TOKEN或者appId token |
| clientId | string | 必填 | 播放主体ID：比如故事机或者布丁的SN |
| userId | string | 可选 | 触发播放的客户端ID，用户点播就是用户ID，语音和设备交互就是设备ID |
| from | string | 必填 | 开始ID |
| size | int | 必填 | 返回结果数 |
| order | string | 必填 | 排序方式，desc-逆序（ID倒排，从大到小），asc-正序 |

返回示例

```
{
    "result": 0,
    "msg": "success",
    "data": {
        "count": 1,
        "playrecords": [
            {
                "id": "9",
                "appId": "pudding1s",
                "production": "",
                "clientId": "10110000002003C7",
                "userId": "ps:5724e37aa1bfd42510b52256ec620b17",
                "resDB": "aires",
                "albumId": "4",
                "currentLength": 20,
                "length": 250,
                "inputType": 0,
                "time": 1501836847,
                "resId": "aires:486237",
                "resource": {
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
                    },
                    "favoriteId": ""
                }
            }
        ]
    }
}
```

其中

| 参数 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.count | int | 记录数 |
| data.playrecords\[\].id | string | 历史记录ID |
| data.playrecords\[\].resDB | string | 资源所属库 |
| data.playrecords\[\].resId | string | 资源ID |
| data.playrecords\[\].production | string | 设备产品线 |
| data.playrecords\[\].clientId | string | 播放主体ID |
| data.playrecords\[\].albumId | string | 歌单ID |
| data.playrecords\[\].currentLength | int | 当前播放进度 |
| data.playrecords\[\].inputType | int | 点播类型： 0-语音点播，1-文本输入 2-app点播 3-续播 |
| data.playrecords\[\].domainId | int | 场景ID（AI场景，暂时可忽略） |
| data.playrecords\[\].length | int | 资源长度（因为资源文件的变更，可能和实际资源长度不一致，这里只用于和currentLength判定代表是否播放完成） |
| data.playrecords\[\].time | int | 最后更新时间（UNIX时间戳） |
| data.playrecords\[\].resource | object | 资源详情，参考： |



