**取消收藏**

接口: /favorite/del

方法： POST

示例： [http://player.roobo.net/favorites/del](http://player.roobo.net/favorites/del)

请求参数

```
{
   "appId" : "QaNCagiMWCdGbGSj",
   "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
   "clientId": "1011000000101005",
   "userId": "ps:5724e37aa1bfd42510b52256ec620b17",
   "production":"pudding1s",
   "resIds":["aires:100","aires:200"],
   "albumIds" : ["100"],
   "favoriteIds" : ["100"]
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string |  | 应用ID |
| clientId | string |  | 设备ID |
| userId | string | 是 | 取消收藏的用户ID |
| production | string | 是 | 产品线 |
| resIds\[\] | string | 是 | 需要取消收藏的资源ID |
| albumIds\[\] | string | 是 | 需要取消收藏的专辑ID |
| favoriteIds\[\] | string | 是 | 需要取消收藏的收藏ID |



返回值

```
{
  "result": 0,
  "msg": "success"
}
```



