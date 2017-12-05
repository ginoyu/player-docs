**创建自定义歌单**

接口： /user-album/new

方法： POST

示例：[https://api.ros.ai/player/user-album/new](https://api.ros.ai/player/user-album/new)

请求参数

```
{
  "appId" : "EvXLUN3xtyON74KY",
  "token" : "786203ce01256d1d590e2d0a1c1f11b62076",
  "clientId" : "1011000000201457",
  "userId" : "ps:5724e37aa1bfd42510b52256ec620b17",
  "parentId" : "100",
  "name" : "歌单标题"
}
```

其中参数意义如下

| 参数 | 类型 | 可选 | 意义 |
| :--- | :--- | :--- | :--- |
| appId | string | 必填 | 应用ID |
| token | string | 必填 | 权限校验TOKEN |
| clientId | string | 必填 | 歌单关联的客户端ID（用户ID或者设备ID） |
| userId | string | 选填 | 标识是哪个用户创建 |
| parentId | string | 是 | 父歌单ID（暂不支持，不填）：当不填或者为空时，表示没有父歌单ID |
| name | string | 必填 | 歌单名称 |

返回内容

```
{
  "result" : 0,
  "msg" : "success",
  "data" : {
    "albumbId" : "1000",
    "parentId" : "100",
    "name" : "歌单标题",
    "imgLarge" : "http://media.roobo.net/appimg/20161114_67fe4ba23ba80b325d4b388838d31853.png",
    "imgSmall" : "http://media.roobo.net/appimg/20161117_fea417c257b8b2826f801d41a3a48931.jpg"
  }
}
```

其中

| 参数 | 类型 | 意义 |
| :--- | :--- | :--- |
| data.albumbId | string | 自建歌单ID |
| data.parentId | string | 父歌单ID（暂不支持） |
| data.name | string | 自建歌单标题 |
| data.imgLarge | string | 自建歌单大图（预留） |
| data.imgSmall | string | 自建歌单小图（预留） |



