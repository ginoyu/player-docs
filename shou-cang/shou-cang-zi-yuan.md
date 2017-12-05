**收藏资源**

接口:  /favorites/add-resource

方法： POST

示例： [https://api.ros.ai/player/favorites/add-resource](https://api.ros.ai/player/favorites/add-resource)

请求参数

```
{
    "appId" : "EvXLUN3xtyON74KY",
    "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
    "clientId":"1011000000101005",
    "userId":"ps:5724e37aa1bfd42510b52256ec620b17",
    "resId" : "aires:23",
    "albumId" : "323",
    "bind" : "device"
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| userId | string | 选填 | 执行收藏的用户ID |
| clientId | string | 必填 | 设备id |
| resId | string | 必填 | 收藏资源ID |
| albumId | string | 选填 | 资源所属的专辑ID |
| bind | string | 选填 | 收藏关联到设备上还是用户上； device-clientId有效，user-userId有效（默认值） |

返回值：

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



