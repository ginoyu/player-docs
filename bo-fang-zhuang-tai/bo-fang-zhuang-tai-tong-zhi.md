**播放状态通知回调**

当设备使用标准的MQTT服务上报播放状态时，ROOBO可以调用第三方HTTP接口，通知第三方服务设备播放状态的变更，以便第三方服务处理业务逻辑，通知客户端状态变化等等。

接口：第三方提供

方法： POST

请求参数： 

```
{
    "appId" : "EvXLUN3xtyON74KY",
    "clientId" : "10110000002003C7",
    "resource":{
        "resId":"aires:485965",
        "type":1,
        "name":"雨后",
        "favoriteId":"1000",
        "length":259,
        "content":"http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3",
        "artist":"歌手",
        "album":{
            "id":"100",
            "name":"测试",
            "imgLarge":"http://i.gtimg.cn/music/photo/mid_album_300/X/X/004G5J350sVsXX.jpg",
            "imgSmall":"http://i.gtimg.cn/music/photo/mid_album_300/X/X/004G5J350sVsXX.jpg"
        },
        "playUrls":{
            "normal":{
                "size":4072551,
                "url":"http://dwn.roo.bo/voices/songs/koudai/be9c171e1fbba48d3bd1f42b5d19b6f9.mp3"
            }
        }
    },
    "status":"ready",
    "offset":0,
    "trigger":"album",
    "timestamp":1478866368,
    "playmode":"random"
}
```

其中各参数意义参考： [获取播放状态](/bo-fang-zhuang-tai/huo-qu-bo-fang-zhuang-tai.md)



第三方服务返回的HTTP Code值是200代表响应成功

