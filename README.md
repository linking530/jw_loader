# jw_loader 这是一个 quick-cocos2d-x 的热更新的独立小项目
基于 quick-cocos2d-x 3.3 lua 的热更新小项目, 无需对引擎进行改造， 小巧简洁，无需强后台支持，支持按渠道开放更新，android与ios真机测试通过！

## 运行条件
quick-cocos2d-x 3.3 版本（3.6社区版需要做些改动，参见示例工程的说明）的android或IOS真机

## 主要特性
单个ZIP包，不依赖quick本身的framework，不与项目本身代码混合
这个升级模块本身也可以被更新
支持按渠道来开放更新
支持指定渠道的更新跳转
支持环境ID的判断，以避免误更新
弱后台需求，很多热更新方案中都需要比较强的后端接口配合，此方案
只需要将静态文件上传至WEB服务器即可，不需要动态语言后台的支持，
当然你也可以根据自己的需求去改造。

## 关联项目
https://github.com/uhoohei/jw_loader_samples.git
关联的示例项目，以及python的资源打包脚本

## 变更记录
1.版本热更新检测依据修改了
2.build脚本是否需要修改？编译文件名的机制是否要更改? 添加一个字段scriptVersion，但本身编译的机制不修改
3.下载文件后保存、比对、更新的逻辑都要重新梳理
4.使用searchPath的机制来将新下载的文件生效，以便不需要对引擎本身进行修改就可更新
5.文件上下比对的方式依然不变
6.去掉原框架中的getres io.getres

## 测试
1.使用脚本版本号作为路径名。
2.添加判断主版本的逻辑，不符合的话跳过。
3.添加运行环境、游戏ID、分支ID的判断，不符合的话跳过。避免错误升级!
