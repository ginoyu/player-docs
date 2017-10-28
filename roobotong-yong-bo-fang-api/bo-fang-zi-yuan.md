**播放指定的资源**



接口： /play

方法： POST

示例： [http://player.roobo.net/play](http://player.roobo.net/play)

请求参数

```
{
  "appId" : "QaNCagiMWCdGbGSj",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId":"3000020000000020",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "resId":"aires:485965",
  "albumId" : "100",
  "cmdProtocol" : "mqtt.v1"
}
```

其中请求参数意义

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填  | 应用ID |
| token | string | 必填  | 产品TOKEN |
| clientId | string | 必填 | 播放设备ID |
| userId | string | 可选 | 执行播放操作的用户ID |
| resId | string | 必填  | 需要播放的资源ID |
| albumId | string | 可选 | 该资源关联的歌单ID，用于上一首，下一首时根据歌单ID自动进行 |
| cmdProtocol | string | 可选 | 是否推送标准播放命令给设备（具体MQTT消息格式参考\*\*） |



返回值

```
{
    "result":0,
    "msg":"success"
}
```



