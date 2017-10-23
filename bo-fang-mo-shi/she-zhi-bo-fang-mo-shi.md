**设置播放模式**

接口： /playmode/set

方法：POST

示例：[http://player.roobo.net/playmode/set](http://player.roobo.net/playmode/set)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "production" : "storybox",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "1011000000201457",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "mode" : "random"
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string |  | 应用ID |
| production | string | 是 | 产品线 |
| userId | string | 是 | 执行设置模式的用户ID |
| clientId | string |  | 用户或设备id， 收藏关联到该ID上 |
| mode | string |  | 播放模式random - 随机播放order - 顺序播放cycle - 全部循环repeat - 单曲循环 |

返回值

```
{
  "result" : 0,
  "msg" : "success"
}
```



