**批量获取资源详情**

接口： /resources/detail

方法： POST

示例： [http://player.roobo.net/resources/detail](http://player.roobo.net/resources/detail)

请求参数：

```
{
    "appId":"QaNCagiMWCdGbGSj",
    "token":"786203ce01256d1d590e2d0a1c1f11b62076",
    "clientId":"3000020000000020",
    "resIds":[
        "aires:485965"
    ]
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string |  | 应用ID |
| token | string |  | 产品TOKEN |
| clientId | string | 是 | 播放主体ID |
| resIds\[\] | string |  | 资源ID列表 |

返回示例

```
{
    "result":0,
    "msg":"success",
    "data":{
        "list":[
            {
                "resId":"aires:485965",
                "type":1,
                "name":"雨后",
                "length":259,
                "content" : "http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3",
                "artist":"歌手",
                "album":{
                    "id":100,
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
        ]
    }
}
```

其中

| 返回值 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.list\[\].resId | string | 内容ID |
| data.list\[\].type | int | 内容类型： 0-文本， 1-音频URL |
| data.list\[\].name | string | 资源名称 |
| data.list\[\].artist | string | 歌手信息 |
| data.list\[\].length | int | 资源时长 |
| data.list\[\].content | string | 默认播放连接/内容 |
| data.list\[\].artist | string | 歌手 |
| data.list\[\].album.id | int | 歌单ID，（QQ音乐目前歌单都是0） |
| data.list\[\].album.name | string | 歌单名称 |
| data.list\[\].album.imgLarge | string | 专辑的大封面 |
| data.list\[\].album.imgSmall | string | 专辑的小封面 |
| data.list\[\].playUrls\[\].normal.size | int | 普通版本文件大小 |
| data.list\[\].playUrls\[\].normal.url | string | 普通版本播放连接 |



