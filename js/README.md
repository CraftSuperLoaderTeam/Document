# JavaScript

本文档介绍了您如何将由`JavaScript`语言编写的插件装载进您的服务端

<hr>

## 🎯寻找

* 您可以在以下网站寻找关于CSL的插件

[像素工坊](https://www.pixelecraft.com/) 

* 像素工坊是CraftSuperLoader的合作伙伴,一个很不错的交流论坛!在里面您可以找到很多关于Minecraft的资源！

[幻梦互联](https://www.mcppl.cn)

* 幻梦互联是CraftSuperLoader的上层机构,旗下有`DotCS` `星服助手`等多个产品

!> 幻梦互联的网站貌似寄掉了,您唯一可访问的只有其用户中心的网站[zeus.mcppl.cn](https://zeus.mcppl.cn)

## 🚅准备

* 请您在装载前详细查看该插件作者对插件的介绍,以防插件的版本与服务端版本不匹配导致插件无法成功加载

* 因该语言插件的结构特殊性,您从各种渠道下载到的插件可能为`*.zip`或`*.7z`等压缩包格式,请将其解压后放入服务端核心所在目录中的`jsscripts`文件夹内

## 🍳加载

* 请时刻留意服务端控制台输出信息,以检查插件输出是否有报错

* 如果您不确定是否有插件加载错误,或者游玩时发现功能异常,可以在控制台或者游戏聊天栏内输入
```MinecraftCommand
/js list
/js
```
用于查看CSL所有识别到的插件,其中绿色显示为正在运行的插件,而红色显示则为因为初始化或者运行时发生无法解决的异常而停用的插件

## 🔌卸载

* 插件在服务端运行时是不可被删除的,如果强制删除文件可能会造成服务端崩溃或者游戏功能异常

* 在服务端彻底关闭时,您可以自由对插件进行增添或者删除的操作

## 热加载/卸载

* CraftSuperLoader几乎对每一种语言的插件都提供了热加载和卸载的命令,方面您自由操作和调试

热加载
```MinecraftCommand
/js load <dir_name>  
<dir_name>必须为jsscripts文件夹内所拥有的文件夹
```

热卸载
```MinecraftCommand
/js disable <plugin_name>
<plugin_name>必须为插件列表中绿色正在运行的插件
```