**模块列表**

接口： /cms/modules

方法：POST

示例：[http://player.roobo.net/cms/modules](http://player.roobo.net/cms/modules)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "10110000002003C7",
  "tags" : []
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必选 | 应用ID |
| clientId | string | 可选 | 用于绑定收藏的用户ID |
| tags\[\] | string | 必选 | 过滤标签 |

返回值

```
{
    "result": 0,
    "msg": "success",
    "data": {
        "total": 2,
        "modules": [
            {
                "id": "5",
                "name": "gagaagaga",
                "icon": "http://dwn.roo.bo/voices/songs/test/31e81c7b2323694c53b491691f20998e.jpg",
                "attr": "mod",
                "description": "",
                "contents": [
                    {
                        "id": "6",
                        "type": "audio",
                        "name": "hello content",
                        "content" : "http://dwn.roo.bo/voices/songs/test/31e81c7b2323694c53b491691f20998e.jpg",
                        "img": "",
                        "tags": []
                    }
                ]
            },
            {
                "id": "1",
                "name": "4444",
                "icon": "http://dwn.roo.bo/voices/songs/test/31e81c7b2323694c53b491691f20998e.jpg",
                "attr": "ad",
                "description": "",
                "contents": [
                    {
                        "id": 1,
                        "type": "ad",
                        "content": "http://www.baidu.com",
                        "name": "喜羊羊",
                        "img": "gaga",
                        "tags": []
                    }
                ]
            }
        ]
    }
}
```

各返回值意义如下

| 返回值 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.total | int | 模块总数量 |
| data.modules\[\].id | string | 模块id |
| data.modules\[\].name | string | 模块名字 |
| data.modules\[\].attr | string | 模块类型：ad-广告模块；mod-普通模块； |
| data.modules\[\].description | string | 模块介绍 |
| data.modules\[\].icon | string | 模块图标 |
| data.modules\[\].contents\[\].id | string | 内容ID |
| data.modules\[\].contents\[\].name | string | 内容名称 |
| data.modules\[\].contents\[\].description | string | 内容详细描述 |
| data.modules\[\].contents\[\].img | string | 内容图片 |
| data.modules\[\].contents\[\].type | string | 内容类型： album-歌单；ad-广告内容；audio-歌曲； |
| data.modules\[\].contents\[\].content | string | 内容，受type影响： album-歌单ID， audio-资源URL；ad-广告的跳转 |
| data.modules\[\].contents\[\].tags\[\] | string | 运营标识：new，hot；年龄标识：one,two,three; |

目前支持的data.attr类型

| data.attr | 类型意义 |
| :--- | :--- |
| mod | 普通模块 |
| cls | 分类视图 |
| ad | 广告位（轮播图） |



