**歌单资源列表**

歌单由资源组成，下面的接口用于获取资源列表

接口： /resources/list

方法： POST

示例：  https://{server}/player/resources/list

请求参数

```
{
    "appId":"QaNCagiMWCdGbGSj",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "clientId" : "10110000002003C7",
    "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
    "albumId" : "100",
    "queryAlbumInfo" : true,
    "page" : 1,
    "bind" : "user",
    "count" : 20
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| token | stirng | 必填 | TOKEN |
| clientId | string | 可选 | 用户ID，用于返回收藏相关信息 |
| appId | string | 必填 | 应用ID |
| albumId | string | 必填 | 歌单ID |
| page | int | 可选 | 分页页数，默认是1 |
| count | int | 可选 | 每页大小，默认是20， 最大100 |
| queryAlbumInfo | bool | 可选 | 是否返回当前歌单详情（默认值是true） |
| bind | string | 可选 | 收藏关联到设备上还是用户上； device-clientId有效，user-userId有效（默认值） |
| userId | string | 可选 | 当前查询的用户ID，用于检查收藏；当bind为user时有效 |

返回值

```
{
    "result":0,
    "msg":"success",
    "data":{
        "total":1,
        "list":[
            {
                "resId":"aires:485965",
                "type":1,
                "name":"雨后",
                "favoriteId":"1000",
                "length":259,
                "content" : "http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3",
                "artist":"歌手",
                "playUrls":{
                    "normal":{
                        "size":4072551,
                        "url":"http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3"
                    }
                }
            }
        ],
        "album":{
            "id":"100",
            "name":"测试",
            "imgLarge":"http://i.gtimg.cn/music/photo/mid_album_300/X/X/004G5J350sVsXX.jpg",
            "imgSmall":"http://i.gtimg.cn/music/photo/mid_album_300/X/X/004G5J350sVsXX.jpg"
        }
    }
}
```

其中

| 返回值 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.total | int | 资源总数 |
| data.list\[\].resId | string | `收藏ID，如果没有收藏为0` |
| data.list\[\].type | int | 内容类型： 0-文本， 1-音频URL |
| data.list\[\].name | string | 资源名称 |
| data.list\[\].score | int | 资源评分 |
| data.list\[\].favoriteId | string | 收藏ID（当接口中传了用户ID时，此字段有效，否则返回空字符串） |
| data.list\[\].artist | string | 歌手信息 |
| data.list\[\].length | int | 资源时长 |
| data.list\[\].content | string | 默认播放连接/内容 |
| data.list\[\].artist | string | 歌手 |
| data.list\[\].playUrls\[\].normal.size | int | 普通版本文件大小 |
| data.list\[\].playUrls\[\].normal.url | string | 普通版本播放连接 |
| data.album.id | string | 歌单ID |
| data.album.name | string | 歌单名称 |
| data.album.imgLarge | string | 专辑的大封面 |
| data.album.imgSmall | string | 专辑的小封面 |



