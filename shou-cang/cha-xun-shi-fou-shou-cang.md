**批量查询是否收藏**



接口: /favorite/query

方法： POST

示例： [http://player.roobo.net/favorites/query](http://media_player.roobo.net/favorites/del)

请求参数：

```
{
    "appId" : "QaNCagiMWCdGbGSj",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "userId":"ps:5724e37aa1bfd42510b52256ec620b17",
    "clientId":"1011000000101005",
    "production":"pudding1s",
    "resIds" : [ "aires:23" ],
    "albumIds" : [ "100" ]
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string |  | 应用ID |
| userId | string | 是 | 过滤指定用户ID收藏的 |
| clientId | string |  | 设备IDID |
| production | string | 是 | 产品线 |
| resIds\[\] | string | 是 | 查询的资源ID |
| albumIds\[\] | string | 是 | 查询的专辑ID |



返回示例

```
{
  "result": 0,
  "msg": "success",
  "data": {
    "resources": [
      {
        "favoriteId": "47",
        "production": "pudding1s",
        "userId": "ps:5724e37aa1bfd42510b52256ec620b17",
        "clientId": "1011000000101005",
        "resId": "aires:23",
        "alumbId" : "232",
        "time": 1478246159
      }
    ],
    "albums" : []
  }
}
```



