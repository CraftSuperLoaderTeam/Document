# JavaScript 环境

本文档介绍了您如何创建一个`JavaScript`脚本插件环境,并如何发布

<hr>

## 准备

* 您需要一个好的IDE(集成开发环境)或者编辑器,我们建议您使用`VisualStudioCode`或者`WebStorm`

* 单独在您的任意位置创建一个文件夹,文件夹名与插件名要一致

以下是目录大致结构
```dir
YourPlugin
 |
 ├- plugin.yml -插件的基本信息
 ├- index.js -插件主要脚本,名字可以自定义,但需要在plugin.yml中指定
 └- config.yml -插件配置文件
```

## 配置信息

* 在插件目录中,您需要创建一个叫做`plugin.yml`的文件,里面记载了该插件的所有信息
以下是文件的基本内容
```yaml
#你的插件名称
name: YourName
#插件主文件名
main: index.js
#插件描述
description: A scl script plugin.
#插件作者
author: XIAOYI12
```

* 其中`main`选项设置的是你主文件的名词,我们建议为`index.js`但是您可以自定义文件名称

## 基本代码

* 根据您设置的插件主文件,您需要插入以下基本代码

```js
function enable(){

}

function disable(){

}
```

### enable
* 插件加载时调用,可以进行基本的依赖库判断,配置文件初始化,以及命令和事件的注册等功能

### disable
* 插件卸载时调用,可以用于注销创建的协程管理器,保存配置信息等插件收尾工作

## 配置文件
* 用于记录插件基本的配置信息,您可以用于插件功能开关以及数值设置等,详细操作接口见[JavaScript-API](js/api.md)