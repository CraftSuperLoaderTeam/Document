# JavaScript API 文档

CSL的JS以最大化程度兼容`LLSE`,但是其开发也有些许不同,您如果有开发LLBDS脚本插件的经验,那么不需要做过大改动即可让您的插件在CSL中运行

## 全局实例对象

### Console : CraftBukkit日志系统

`Console`对象在您脚本任何位置都可直接使用,其内部实现对接了CraftBukkit的`Log4j`日志系统,但是我们延申的API非常简洁,您无需过多操作即可调用

#### console.info
* 该函数作用为向日志记录器发送一条`INFO`级别的日志
```js
console.info("Hello! World!")
```
```shell
[xx:xx:xx][ThreadName/INFO]: Hello! World!
```

#### console.log
* 该函数作用为向日志记录器发送一条`INFO`级别的日志,与`console.info`作用相同
```js
console.log("Hello! World!")
```
```shell
[xx:xx:xx][ThreadName/INFO]: Hello! World!
```

#### console.warn
* 该函数作用为向日志记录器发送一条`WARN`级别的日志
```js
console.warn("Hello! World!")
```
```shell
[xx:xx:xx][ThreadName/WARN]: Hello! World!
```

#### console.error
* 该函数作用为向日志记录器发送一条`ERROR`级别的日志
```js
console.error("Hello! World!")
```
```shell
[xx:xx:xx][ThreadName/ERROR]: Hello! World!
```


!> 一般情况下不建议使用该API,这条级别日志的出现一般代表这服务端出现崩溃,滥用会造成日志系统混乱,使报错结果极难分析

### Minecraft : CSL顶级API接口

`Minecraft`对象与`Console`相同,都可以在任意位置使用,其内部实现的关于事件发送,命令注册,以及服务端的各种配置信息等

#### mc.runcmd
* 该函数作用为以控制台身份向游戏内发送一条命令
* 返回值`bool` `true`:执行成功/`false`:执行失败
```js
mc.runcmd("/say Hello!")
```

#### mc.newCommand
* 该函数作用为向服务端注册一条命令
* 返回值`Command`
``` js
function command(sender,args){
    //sender -命令发送方(控制台/实体/玩家)
    //args -命令参数
}
mc.newCommand("say",command)
```

#### mc.setMotd
* 该函数作用为设置服务端显示的`MOTD`标题
* `&`会自动转译成`§`字符,`&&`会转译成`&`字符
* 返回值`NULL`
``` js
mc.setMotd("&eHello! CraftSuperLoader!")
```

#### mc.getCSLVersion
* 该函数作用为获取CSL服务端的版本

!> 该API并不是获取MC的版本号,CSL版本号只能有助于您判断CSL提供的接口是否匹配

* 返回值`string`
``` js
let version =  mc.getCSLVersion()
console.log(version)
```
```shell
[xx:xx:xx][ThreadName/INFO]: Alpha-R0.4-SNAPSHOT
```

#### mc.getVersion
* 该函数作用为获取Minecraft游戏版本

* 返回值`string`
``` js
let version =  mc.getVersion()
console.log(version)
```
```shell
[xx:xx:xx][ThreadName/INFO]: 1.12.2
```

#### mc.getPlayer
* 该函数作用为获取一个在线玩家的实例
* 返回值`Player`
``` js
let player = mc.getPlayer("XIAOYI12")
```

#### mc.getOnlinePlayers
* 该函数作用为获取所有在线玩家的数组
* 返回值`Array<Player>`
``` js
let player = mc.getOnlinePlayers()
```