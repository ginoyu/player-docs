**上报播放状态**

播放状态可以通过两种方式上报：

（1） ROOBO通用的MQTT服务，当设备接入ROOBO的MQTT后，可以使用ROOBO SDK上报播放状态（参考[MQTT通用播放协议](/chapter1/roobotong-yong-bo-fang-api/mqttshang-bao-bo-fang-zhuang-600126-jin-du.md)）

（2）通用的播放状态上报HTTP接口，第三方设备直接调用或者由第三方代理调用上报播放状态

HTTP接口

接口： /status/report

方法： POST

示例： [http://player.roobo.net/status/report](http://player.roobo.net/status/report)

请求参数

```
{
  "appId":"EvXLUN3xtyON74KY",
  "clientId":"10110000002003C7",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "resId" : "music:2811790",
  "albumId" : "100",
  "status" : "pause",
  "offset" : 15,
  "timestamp" : 1503843677000
}
```

其中：

| 参数 | 类型 | 可选 | 含义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用标识 |
| clientId | string | 必填 | 设备ID |
| resId | string | 必填 | 资源ID |
| albumId | string | 选填 | 资源所属的歌单ID，当资源属于多个歌单时有用 |
| sid | string | 选填 | session id；当资源比较复杂（互动故事等）是由多段组成的时候；该参数用于标识当前播放的是哪一小段 |
| status | string | 必填 | 播放状态，可选值：ready 准备播放-初始值loading 播放加载中play 播放中pause 暂停stop 结束 |
| offset | int | 选填 | 暂停点,单位秒 |
| timestamp | int | 选填 | 设备当前时间戳，毫秒级UNIX时间戳 |

返回内容

```
{
  "result": 0,
  "msg": "success"
}
```



