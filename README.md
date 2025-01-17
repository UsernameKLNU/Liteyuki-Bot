<div align="center">

![图片](/docs/img/luxun.png)

# Liteyuki Bot


### 轻雪机器人

#### 基于[Nonebot](https://v2.nonebot.dev/)库的QQ机器人

</div>

## 简介

作者没有女朋友那段时间一个人过于寂寞，便写了这个bot来陪伴自己，顺便学习一些相关知识。使用了Nonebot库，继承了Nonebot的大部分优点，作者自己造了很多轮子和~~屎山~~。有相对简洁的插件管理功能。代码很烂，自己用的。

## 安装

#### 1.安装Python3.10运行环境
##### Windows
- 机器人是需要Python运行环境的，就像我的世界Java版需要Java运行环境
- 转到[下载页面](https://www.python.org/downloads/release/python-3100/)，选择你需要的版本下载，记得勾选Add Python to environment variables
- 不会请看[这里](https://zhuanlan.zhihu.com/p/344887837)
##### Linux
- 如果发行版已提供Python3.10的软件包，则直接通过包管理器安装即可。若无，请参考[此教程](https://blog.csdn.net/weixin_43935402/article/details/121416812)
#### 2.安装机器人适配器（以[go-cqhttp](https://docs.go-cqhttp.org/)为例）

- 这是一个适配器，通俗易懂来说就是一个特殊的qq客户端，它能接收消息并上报给机器人，就好比手机qq能将消息通知给你，而此时的你是机器人
- 转到[下载页面](https://github.com/Mrs4s/go-cqhttp/releases)，选择适合你系统的版本进行下载
- 配置，选择反向websocket通信方式，详细配置方法见[go-cqhttp](https://docs.go-cqhttp.org/guide/quick_start.html)
  。最后在config.yml的servers.ws-reverse.universal处填入`ws://127.0.0.1:你的端口号/onebot/v11/ws`

#### 3.下载(更新)机器人

- 安装[Git](http://git-scm.com/)命令行工具，并使用以下命令克隆本仓库：
   ```
   git clone https://github.com/snowyfirefly/Liteyuki
   ```
  或者点击github页面那个绿色的`code`按钮，再点击download ZIP，并解压ZIP（不推荐）
- 打开根目录（包含`bot.py`文件的目录），右键单击空白处，在此打开终端/cmd，输入`pip install -r requirements.txt`并回车，等待完成
- 给Bot发送`/update`以更新，若此方法更新失败，请手动下载仓库源码覆盖老文件

#### 4.启动

- 在go-cqhttp配置好后，请去按照本页面内容配置机器人
- 启动go-cqhttp(请一定用命令行启动)
- 启动机器人，点击`bot.py`或用命令行启动

## 配置

- 首次启动机器人时，会默认生成BOT配置文件.env，大多数情况下，你只需要配置PORT使它和go-cqhttp中的端口相同。如果你想给BOT改名，修改NICKNAME的值即可。修改完后手动重启BOT端

- 发送liteyuki，若回复测试成功即为安装完成。

- 部分插件正常工作需要[手动配置](/docs/config.md)`data/g0.json`。

## 使用

- 请参阅[使用手册](/docs/usage.md)

## 常见问题

#### 0.更新频率

- 大多数情况下是每天一次，保持更新，遇到无解bug请更新，若还是有bug请反馈。

#### 1.机器人不响应群聊消息

- 机器人加入群聊需要超级用户手动开启，私聊bot发送`群聊启用 <群号>`。
- .env中COMMAND_START中没有`""`空命令前缀选项，命令需接斜杠。

#### 2.bot无法注册，收不到邮箱验证码

- BOT注册默认情况下无需邮箱验证码，用户可根据需求打开，想要开启需要在`data/g0.json`中配置BOT注册验证码发送的邮箱和邮箱登录码，并且邮箱要开启POP3/SMTP/IMAP服务，详细请查看[手动配置](https://github.com/snowyfirefly/Liteyuki/blob/master/docs/config.md)。
- 邮箱配置无误后，若用户未收到验证码请检查垃圾邮件，90%的可能在那里面。

#### 3.其他问题

- 请提交issue
- 加我qq[2238694726](http://ti.qq.com/friend/recall?uin=2238694726)


#### 4.捐赠
- 作者已经吃不起饭，睡大街了(doge)，如果你觉得此项目不错的话可以给作者一些鼓励，这将会是我继续维护的动力
- 微信-WeChat
  ![捐赠：微信](/docs/img/donate_wechat.png)
- 支付宝-Alipay
  ![捐赠：支付宝](/docs/img/donate_alipay.png)
