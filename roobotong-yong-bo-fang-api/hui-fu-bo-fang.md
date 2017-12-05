**恢复播放**

接口： /device/resume

方法： POST

示例： [https://api.ros.ai/player/device/resume](https://api.ros.ai/player/device/resume)

请求参数

```
{
  "appId" : "QaNCagiMWCdGbGSj",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId":"3000020000000020",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "cmdProtocol" : "mqtt.v1"
}
```

其中各参数意义

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | 产品TOKEN |
| clientId | string | 必填 | 播放设备ID |
| userId | string | 可选 | 执行暂停操作的用户ID |
| cmdProtocol | string | 可选 | 是否推送标准暂停命令给设备（具体MQTT消息格式参考\*\*） |

返回值

```
{
  "result" : 0,
  "msg" : : "success"
}
```



