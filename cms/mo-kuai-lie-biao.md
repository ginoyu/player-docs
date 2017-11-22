**单个资源详情**

接口： /resources/info

方法： POST

示例：[http://player.roobo.net/resources/info](http://player.roobo.net/resources/info)

请求参数：

```
{
    "appId":"QaNCagiMWCdGbGSj",
    "token":"786203ce01256d1d590e2d0a1c1f11b62076",
    "clientId":"3000020000000020",
    "resId":"aires:485965",
    "albumId" : "100",
    "bind" : "device"
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | 产品TOKEN |
| clientId | string | 可选 | 设备ID |
| resId | string | 必填 | 需要查询的资源ID |
| albumId | string | 可选 | 该资源关联的歌单ID，用于同时查询该歌单信息如果不指定，返回与该资源关联的第一个歌单 |
| bind | string | 可选 | 收藏关联到设备上还是用户上； device-clientId有效，user-userId有效（默认值） |

返回示例

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

其中

| 返回值 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.resId | string | 内容ID |
| data.favoriteId | string | 收藏ID（当接口中传了用户ID时，此字段有效，否则返回空字符串） |
| data.type | int | 内容类型： 0-文本， 1-音频URL |
| data.name | string | 资源名称 |
| data.score | int | 资源评分 |
| data.fid | int | 收藏ID |
| data.artist | string | 歌手信息 |
| data.length | int | 资源时长 |
| data.content | string | 默认播放连接/内容 |
| data.artist | string | 歌手 |
| data.album.id | string | 歌单ID |
| data.album.name | string | 歌单名称 |
| data.album.imgLarge | string | 专辑的大封面 |
| data.album.imgSmall | string | 专辑的小封面 |
| data.playUrls\[\].normal.size | int | 普通版本文件大小 |
| data.playUrls\[\].normal.url | string | 普通版本播放连接 |

注：

* 如果指定的歌单ID无效，或者资源没有关联的歌单， data.album 返回 null



