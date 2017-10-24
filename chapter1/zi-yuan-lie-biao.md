**歌单资源列表**

歌单由资源组成，下面的接口用于获取资源列表

接口： /resources/list

方法： POST

示例：  [http://player.roobo.net/resources/list](http://player.roobo.net/resources/list)

请求参数

```
{
    "appId":"QaNCagiMWCdGbGSj",
    "production":"pudding1s",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "clientId" : "10110000002003C7",
    "albumId" : "100",
    "queryAlbumInfo" : true,
    "page" : 1,
    "count" : 20
}
```

其中

| token | string | 必选 | TOKEN |
| :--- | :--- | :--- | :--- |
| production | string | 可选 | 产品类型 |
| clientId | string | 可选 | 用户ID，用于返回收藏相关信息 |
| appId | string | 必选 | 应用ID |
| albumId | string | 必选 | 歌单ID |
| page | int | 可选 | 分页页数，默认是0 |
| count | int | 可选 | 每页大小，默认是20， 最大100 |
| queryAlbumInfo | bool | 可选 | 是否返回当前歌单详情 |

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
        "album" : null
    }
}
```

其中

| data.total | int | 资源总数 |
| :--- | :--- | :--- |
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
| data.album | object | 歌单详情，参考：[资源详情](/chapter1/zi-yuan-xiang-qing.md) |



