**创建自定义歌单**

接口： /user-album/new

方法： POST

示例：

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "production" : "pudding1s",
  "token" : "o6aSmwOHw4i1gxL_pQGydDOPoaHk",
  "clientId" : "1011000000201457",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "parentId" : "100",
  "name" : "歌单标题"
}
```

其中参数意义如下

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string |  | 应用ID |
| production | string | 是 | 产品线名称 |
| token | string |  | 设备TOKEN或者应用TOKEN |
| clientId | string |  | 歌单关联的客户端ID（用户ID或者设备ID） |
| userId | string | 是 | 当歌单关联到设备上时，userId标识是哪个用户创建 |
| parentId | string | 是 | 父歌单ID，当不填或者为空时，表示没有父歌单ID |
| name | string |  | 歌单名称 |



返回内容

```
{
  "result" : 0,
  "msg" : "success",
  "data" : {
    "albumbId" : "1000",
    "parentId" : "100",
    "name" : "歌单标题",
    "imgLarge" : "",
    "imgSmall" : ""
  }
}
```

其中

| 参数 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.albumbId | string | 自建歌单ID |
| data.name | string | 自建歌单标题 |
| data.imgLarge | string | 自建歌单大图（预留） |
| data.imgSmall | string | 自建歌单小图（预留） |



