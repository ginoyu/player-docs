**模块列表**



接口： /resources/modules

方法：POST

示例： [http://player.roobo.net/resources/modules](http://player.roobo.net/resources/modules)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "10110000002003C7"
}
```

其中

| appId | string | 必选 | 用于认证相关的appId |
| :--- | :--- | :--- | :--- |
| clientId | string | 可选 | 用于绑定收藏的用户ID |
| treeId | string | 必选 | 内容树唯一标识（可以在内容云CMS中找到），ROOBO默认的内容树标识是： |
| 参数 | 类型 | 选项 | 意义 |



返回值

```
{
    "result":0,
    "msg":"success",
    "data":{
        "total":1,
        "modules":[
           {
                "id":"91",
                "name":"新品上架",
                "description":"新品上架",
                "icon":"http://media.roo.bo/images/icon/hot.png",
                "imgThumb":"",
                "imgLarge":"",
                "contents":[
                    {
                        "id":"9729",
                        "favoriteId" : "1000",
                        "name":"安徒生童话",
                        "description":"",
                        "total":17,
                        "imgLarge":"http://media.roobo.net/appimg/20160426_9eee91fc6e3ddd8223e4b52d3589352b.png",
                        "imgThumb":"http://media.roobo.net/appimg/20161019_3e6b8075b2cbb76661df3f3d1548a682.png",
                        "type" : "album",
                        "tags" : ["new"]
                    }
                ]
            }
        ]
    }
}
```

各返回值意义如下

| data.total | int | 模块总数量 |
| :--- | :--- | :--- |
| data.modules | array | 返回模块列表 |
| data.modules\[\].id | string | 模块id |
| data.modules\[\].name | string | 模块名字 |
| data.modules\[\].description | string | 模块介绍 |
| data.modules\[\].icon | string | 模块图标 |
| data.modules\[\].imgThumb | string | 模块小图（？） |
| data.modules\[\].imgLarge | string | 模块大图（？） |
| data.modules\[\].categories\[\].id | string | 歌单ID |
| data.categories\[\].favoriteId | string | 收藏ID（当接口中传了用户ID时，此字段有效，否则返回空字符串） |
| data.modules\[\].contents\[\].name | string | 歌单名称 |
| data.modules\[\].contents\[\].description | string | 歌单详细描述 |
| data.modules\[\].contents\[\].imgLarge | string | 歌单大图链接 |
| data.modules\[\].contents\[\].imgThumb | string | 歌单小图链接 |
| data.modules\[\].contents\[\].type | string | 歌单类型： album-此歌单只包含资源；category-此歌单只包含子歌单 |
| data.modules\[\].contents\[\].tags\[\] | string | 运营标识： ROOBO默认支持 new-当前资源是新资源， hot-当前资源是热度资源 |
| data.modules\[\].contents\[\].total | int | 此歌单下包含的子歌单（或者资源）的总数量 |



