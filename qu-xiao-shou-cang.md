**取消收藏**

接口: /favorites/del

方法： POST

示例： [https://api.ros.ai/player/favorites/del](https://api.ros.ai/player/favorites/del)

请求参数

```
{
   "appId" : "QaNCagiMWCdGbGSj",
   "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
   "clientId": "1011000000101005",
   "userId": "ps:5724e37aa1bfd42510b52256ec620b17",
   "resIds":["aires:100","aires:200"],
   "albumIds" : ["100"],
   "favoriteIds" : ["100"],
   "bind" : "device"

}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| clientId | string | 必填 | 设备ID |
| userId | string | 选填 | 取消收藏的用户ID |
| resIds\[\] | string | 选填 | 需要取消收藏的资源ID（暂不支持） |
| albumIds\[\] | string | 选填 | 需要取消收藏的专辑ID（暂不支持） |
| favoriteIds\[\] | string | 选填 | 需要取消收藏的收藏ID |
| bind | stri6ng | 选填 | 收藏关联到设备上还是用户上； device-clientId有效，user-userId有效（默认值） |

返回值

```
{
  "result": 0,
  "msg": "success"
}
```



