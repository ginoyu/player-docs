**查询播放模式**

接口： /playmode/get

方法：POST

示例：[http://player.roobo.net/playmode/get](http://player.roobo.net/playmode/get)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "1011000000201457"
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | 校验TOKEN |
| userId | string | 可选 | 执行设置模式的用户ID |
| clientId | string | 可选 | 用户或设备id， 收藏关联到该ID上 |

返回值

```
{
  "result" : 0,
  "msg" : "success",
  "data" : {
    "mode" : "random"
  }
}
```

其中 data.mode 是播放模式值

