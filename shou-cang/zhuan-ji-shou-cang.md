**收藏专辑**

接口:  /favorites/add-album

方法： POST

示例： [http://player.roobo.net/favorites/add-album](http://player.roobo.net/favorites/add-album)

请求参数

```
{
    "appId" : "QaNCagiMWCdGbGSj",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "clientId":"1011000000101005",
    "userId":"ps:5724e37aa1bfd42510b52256ec620b17",
    "albumId" : "323"
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| userId | string | 选填 | 执行收藏的用户ID |
| clientId | string | 必填 | 设备id |
| data.albumId | string | 选填 | 资源所属的专辑ID |

返回示例

```
{
  "result": 0,
  "msg": "success",
  "data": {
    "favoriteId" : "3355"
  }
}
```

其中

| 参数 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.favoriteId | string | 收藏id |



