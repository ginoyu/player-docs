**歌单列表**

模块由多个歌单组成，且某些歌单可以由子歌单组成；下面的接口用于获取模块/歌单 下的（子）歌单列表

接口： /cms/categories

方法：POST

示例： [https://api.ros.ai/player/cms/categories](https://api.ros.ai/player/cms/categories)

请求参数

```
{
    "appId":"QaNCagiMWCdGbGSj",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "clientId" : "10110000002003C7",
    "moduleId" : "189",
    "albumId" : "100",
    "page" : 1,
    "count" : 20
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | TOKEN |
| clientId | string | 可选 | 用户ID，用于返回收藏相关信息 |
| moduleId | string | 可选 | 模块ID（当获取模块下所有歌单时，传该参数） |
| albumId | string | 可选 | 歌单ID（当获取某个歌单下所有子歌单时，传该参数，暂不支持） |
| page | int | 可选 | 分页，默认是1 |
| count | int | 可选 | 每页大小，默认是20 |

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
        "id" : "189",
        "name" : "热门推荐",
        "attr" : "cls",
        "icon" : "http://media.roobo.net/res/20171106/fb2f4a67a6d839dce20b54047865499c.png",
        "description" : "",
        "list":[
            {
                "id":"9484",
                "favoriteId" : "1000",
                "name":"不一样的卡梅拉",
                "description":"",
                "total":17,
                "imgSmall":"http://media.roobo.net/appimg/20161114_67fe4ba23ba80b325d4b388838d31853.png",
                "imgLarge":"http://media.roobo.net/appimg/20161117_fea417c257b8b2826f801d41a3a48931.jpg",
                "type":"album",
                "tags" : ["new"]
            }
        ]
    }
}
```

其中返回值意义如下

| 返回值 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.total | int | 模块或者歌单下所有的（子）歌单数量 |
| data.id | string | 输入ID |
| data.name | string | 模块名 |
| data.attr | string | 模块类型 |
| data.icon | string | 图标 |
| data.description | string | 模块详细描述 |
| data.categories\[\].id | int | 歌单ID |
| data.categories\[\].favoriteId | string | 收藏ID（当接口中传了用户ID时，此字段有效，否则返回空字符串） |
| data.categories\[\].type | string | 歌单类型： album-此歌单只包含资源；category-此歌单只包含子歌单 |
| data.categories\[\].imgLarge | string | 歌单大图链接 |
| data.categories\[\].imgSmall | string | 歌单小图链接 |
| data.categories\[\].name | string | 歌单名称 |
| data.categories\[\].description | string | 歌单详细描述 |
| data.categories\[\].tags\[\] | string | 运营标识： ROOBO默认支持 new-当前资源是新资源， hot-当前资源是热度资源 |
| data.categories\[\].total | int | 此歌单下包含的子歌单（或者资源）的总数量 |



