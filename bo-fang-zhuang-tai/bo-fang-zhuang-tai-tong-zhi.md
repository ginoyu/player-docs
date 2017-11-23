**播放状态通知回调**

当设备使用标准的MQTT服务上报播放状态时，ROOBO可以调用第三方HTTP接口，通知第三方服务设备播放状态的变更，以便第三方服务处理业务逻辑，通知客户端状态变化等等。

接口：第三方提供

方法： POST

请求参数：

```
{
    "appId" : "EvXLUN3xtyON74KY",
    "clientId" : "10110000002003C7",
    "from":"mqtt",
    "topic":"player",
    "action":"play.status.update"
    "timestamp":1478866368
}
```



第三方服务返回的HTTP Code值是200代表响应成功

