**删除历史记录**

接口：/playrecord/del

方法：POST

示例： [https://api.ros.ai/player/playrecord/del](https://api.ros.ai/player/playrecord/del)

请求参数

```
{
    "appId" : "EvXLUN3xtyON74KY",
    "clientId":"1015000000101064",
    "token": "786203ce01256d1d590e2d0a1c1f11b62076",
    "ids" : ["19"]
}
```

其中

| 参数名 | 参数类型 | 意义 |
| :--- | :--- | :--- |
| appId | string | 应用ID |
| clientId | string | 设备ID |
| token | string | 请求TOKEN |
| ids\[\] | string | 历史记录ID |

返回值

```
{
  "result" : 0,
  "msg" : "success"
}
```



