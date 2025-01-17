## Liteyuki Bot的手动配置项

##### Bot在首次运行时会自动创建data/g0.json，所有配置项都在里面，你可以选择手动编辑或也可以通过Bot命令编辑（推荐）

### 手动编辑：

- 此方法较快
- 您必须了解json的格式
- 每次保存时务必保证json没有语法错误
- json配置文件路径为data/g0.json

### 命令编辑

- 此方法较稳妥，只有在语法正确时会保存
- 向bot发送 `设置属性 g 0 <属性名> <属性值>` ，其中最重要的一点是，属性值为字符串时，请务必用引号包起来，不管你用单引号还是双引号，
  若是列表或json对象请先获取，编辑好后再覆盖原有数据
  特殊字符记得用"\\"转义，例如`设置属性 g 0 kami.weather.key "1234567890abcdef"`

#### 可以编辑的属性（其实里面自动生成的都能编辑，只要你知道你在干啥，除下面列出的以外，其他的都为自动配置）

| 属性名                     | 类型     | 默认值     | 说明                                                                                                         |
|-------------------------|--------|---------|------------------------------------------------------------------------------------------------------------|
| `kami.base.verify`      | `bool` | `false` | 新用户是否邮箱验证，默认情况下用户只需要发送注册即可，若启用后记得给邮箱账户开启POP3/IMAP/SMTP服务                                                   |
| `kami.base.email`       | `str`  | `""`    | 仅在`kami.base.verify`为`true`时配置，发送验证邮件的邮箱，                                                                  |
| `kami.base.email_auth`  | `str`  | `""`    | 仅在`kami.base.verify`为`true`时配置，邮箱的授权密码，在你的邮箱服务商获取，                                                         |
| `kami.base.email_user`  | `str`  | `""`    | 仅在`kami.base.verify`为`true`时配置，邮箱的用户名，最好填写邮箱去掉@xxx.com的部分                                                  |
| `kami.base.email_host`  | `str`  | `""`    | 仅在`kami.base.verify`为`true`时配置，邮箱的服务器地址，请见[常用邮箱服务器地址](https://cloud.tencent.com/developer/article/1181227) |
| `kami.weather.key`      | `str`  | `""`    | 和风天气的key，需要去[和风天气](https://console.qweather.com/#/apps)申请，否则无法使用天气插件                                       |
| `kami.weather.key_type` | `str`  | `"dev"` | 和风天气的key类型，商业版填写`"com"`，开发版默认为`"dev"`                                                                      |
| `kami.map.key`          | `str`  | `""`    | 高德地图的key，需要去[高德地图](https://console.amap.com/dev/key/app)申请，否则无法使用高德地图插件                                    ||
| `ignored_users`         | `list` | `[]`    | 机器人要忽略的用户id列表，添加后就算目标用户触发了违禁词也不会响应                                                                         |
| `blocked_users`         | `list` | `[]`    | 和忽略用户差不多，但是仍然会处理目标用户的违禁词                                                                                   |
| `log_mode`              | `bool` | `false` | 是否开启日志模式                                                                                                   |

- json示例

```json
{
    "属性名1": "属性值1",
    "属性名2": "属性值2",
    "属性名3": "属性值3",
    "kami.base.verify": false,
    "ignored_users": [
        114514,
        1919810
    ]
}
```