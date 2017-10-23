**初始化自定义歌单**

用户可以根据指定的歌单ID复制一份新的歌单



接口： /user-album/init

方法： POST

示例： [http://player.roobo.net/user-album/init](http://player.roobo.net/user-album/init)

请求参数



```
{
  "appId" : "EvXLUN3xtyON74KY",
  "production" : "pudding1s",
  "token" : "o6aSmwOHw4i1gxL_pQGydDOPoaHk",
  "clientId" : "1011000000201457",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "newAlbum" : true,
  "albumIds" : [ "10" ]
}
```

其中

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string |  | 应用ID |
| production | string | 是 | 产品线名称 |
| token | string |  | 设备TOKEN或者应用TOKEN |
| clientId | string |  | 歌单关联的客户端ID（用户ID或者设备ID） |
| userId | string | 是 | 当歌单关联到设备上时，userId标识是哪个用户创建 |
| newAlbum | bool |  | 是否需要创建新歌单 |
| albums\[\] | string |  | 需要被初始化的歌单ID如果newAlbum为true，播放服务会根据该歌单ID创建一个新歌单如果newAlbum为false，播放服务会恢复该歌单到原始状态 |

返回值

```
{
  "result" : 0,
  "msg" : "success",
  "data" : {
    "albums" : [
      {
        "albumId": "61260",
        "parentId": "",
        "name": "歌单标题",
        "templateId": "",
        "total": 0,
        "type": "album",
        "imgLarge": "",
        "imgSmall": ""
      }
    ]
  }
}
```

其中

| 返回值 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.albums\[\].albumId | string | 专辑ID（如果是新增的话，是新增专辑ID） |
| data.albums\[\].parentId | string | 父专辑ID |
| data.albums\[\].name | string | 歌单名称 |
| data.albums\[\].templateId | string | 原始歌单ID，如果没有则为空字符串 |
| data.albums\[\].type | string | 类型： 固定为album |
| data.albums\[\].total | int | 歌单下资源数 |
| data.albums\[\].imgLarge | string | 歌单大图 |
| data.albums\[\].imgSmall | string | 歌单小图 |



