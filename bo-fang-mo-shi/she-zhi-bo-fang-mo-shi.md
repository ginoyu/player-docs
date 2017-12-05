**设置播放模式**

接口： /playmode/set

方法：POST

示例：[https://api.ros.ai/player/playmode/set](https://api.ros.ai/player/playmode/set)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "1011000000201457",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "mode" : "random"
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| userId | string | 选填 | 执行设置模式的用户ID |
| clientId | string | 必填 | 设备id |
| mode | string | 必填 | 播放模式 random - 随机播放order - 顺序播放cycle - 全部循环repeat - 单曲循环 |

返回值

```
{
  "result" : 0,
  "msg" : "success"
}
```



