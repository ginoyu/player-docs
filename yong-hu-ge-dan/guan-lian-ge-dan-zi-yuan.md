**关联资源**

该接口可用于增加/删除资源；是一个批量接口

接口： /user-album/resources

方法： POST

示例： [https://api.ros.ai/player/user-album/resources](https://api.ros.ai/player/user-album/resources)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "1011000000201457",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "albumId" : "100",
  "inserts" : ["aires:1000"],
  "removes" : ["aires:200"]
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | TOKEN |
| clientId | string | 必填 | 设备ID |
| albumId | string | 必填 | 歌单ID |
| inserts\[\] | string | 可选 | 待添加的资源ID |
| removes\[\] | string | 可选 | 删除的资源ID |

返回值

```
{
  "result" : 0,
  "msg" : "success"
}
```



