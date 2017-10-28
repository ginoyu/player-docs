**MQTT接入**

第三方设备接入ROOBO的mqtt服务，可以使用ROOBO的mqtt SDK接入，已经封装好了设备接入功能，包含

* 设备注册：SN号，TOKEN分配
* MQTT连接： 和ROOBO服务保持MQTT长连接

SDK下载路径：

SDK说明文档：[ROOBO MQTT 协议文档-v1.3.0.pdf](/ROOBO MQTT 协议文档-v1.3.0.pdf)

**MQTT资源点播**

```
{
    "cmd":"demandMusicOnline",
    "trackListId":"10194",
    "trackId":"341280",
    "url":"http://dwn.roo.bo/voices/songs/test/huanggongdexiaoairen.mp3",
    "downloadUrl":"http://dwn.roo.bo/voices/songs/test/huanggongdexiaoairen.mp3",
    "title":"皇宫的小矮人"
}
```

其中各参数意义

| 参数 | 类型 | 意义 |
| :--- | :--- | :--- |
| trackListId | string | 专辑ID |
| trackId | string | 资源ID |
| url | string | 在线播放URL |
| downloadUrl | string | 离线下载URL |
| title | string | 资源名称 |

**MQTT播放上一首**

```
{
    "cmd" : "backward",
    "trackListId":"10194",
    "trackId":"341280",
    "url":"http://dwn.roo.bo/voices/songs/yiqianlingyiye/huanggongdexiaoairen.mp3",
    "downloadUrl":"http://dwn.roo.bo/voices/songs/yiqianlingyiye/huanggongdexiaoairen.mp3",
    "title":"皇宫的小矮人"

}
```

**MQTT播放下一首**

```
{
    "cmd" : "forward",
    "trackListId":"10194",
    "trackId":"341280",
    "url":"http://dwn.roo.bo/voices/songs/test/huanggongdexiaoairen.mp3",
    "downloadUrl":"http://dwn.roo.bo/voices/songs/test/huanggongdexiaoairen.mp3",
    "title":"皇宫的小矮人"

}
```

**MQTT暂停播放**

```
{
    "cmd" : "pause"
}
```

**MQTT恢复播放**

```
{
    "cmd" : "resume"
}
```

**MQTT播放状态上报**

```
{
    "action":"play.status.report",
    "trackListId":"8068",
    "trackId":"268923767",
    "status":"play",
    "offset":15
}
```



