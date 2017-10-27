**歌单列表**

模块由多个歌单组成，且某些歌单可以由子歌单组成；下面的接口用于获取模块/歌单 下的（子）歌单列表

接口： /resources/categories

方法：POST

示例： [http://player.roobo.net/resources/categories](http://player.roobo.net/resources/categories)

请求参数

```
{
    "appId":"QaNCagiMWCdGbGSj",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "clientId" : "10110000002003C7",
    "moduleId" : "189",
    "albumId" : "100",
}
```

其中

| appId | string | 必选 | 应用ID |
| :--- | :--- | :--- | :--- |
| token | string | 必选 | TOKEN |
| clientId | string | 可选 | 用户ID，用于返回收藏相关信息 |
| moduleId | string | 可选 | 模块ID（当获取模块下所有歌单时，传该参数） |
| albumId | string | 可选 | 歌单ID（当获取某个歌单下所有子歌单时，传该参数） |
| 参数 | 类型 | 可选 | 意义 |

注：

* moduleId和
  albumId两个参数只能填一个，否则服务器会拒绝。
* albumId必须包含子歌单，否则服务器行为不可预期

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

其中返回值意义如下

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





