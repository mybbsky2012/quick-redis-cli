### quick-redis-cli ###

 通用redis-cli终端运维管理快捷脚本 Version 1.1.0<br>
 ( 脚本最后更新时间:2016-10-21 )<br>
 File Name:    quick-redis-cli.sh <br>
 Copyright:    2016 Jack Liu (Liu Jianqiu 秋)<br>
 License:      MIT<br>
 Version:      Version 1.1.0<br>
 
 Author: Jack Liu (Liu Jianqiu 秋)<br>
 Email: ceophp@163.com<br>
 QQ: 1099729311 404691073(work used)
 Created Init By Date: 2016-03-18<br>

【编写原因】<br>
实际工作中几乎每天经常用到redis-cli管理redis实例, 一些重复性的操作习惯用shell脚本流程执行，之前写了个redis-cli的快捷连接脚本，省掉了不少不必要的时间，昨晚抽空闲时间扩展了一下部分功能， 脚本很简单，后续有时间会针对多实例管理加入更多实用功能和批处理redis实例功能。少量服务器暂时用shell实现满足一般操作需求。
后续抽时间用Golang实现编译成二进制执行， 执行效率高点。

脚本1.1.0实现基础功能，后续抽时间更新会集中在特定场景业务批处理上


针对redis-cli的操作经常要反复敲命令，很多业务场景下，一般的redis GUI图形界面管理工具不能很好的处理几个痛点：<br>
1.无论本机还是远程IP管理，针对包含密码的操作，要反复输入密码，且高强度密码为了安全设置复杂，手动输入效率低，且要反复进行制粘贴操作，比较繁琐。
2.在线上生产隔离环境下，可视化GUI类管理软件还要通过代理服务器中转管理不方便也极不安全, 很多运维场景不适用，占用链接资源。
3.在CLI模式下频繁通过堡垒机（跳板机）管理内部隔离的redis实例服务器，IP和密码验证输入重复操作流程多，容易出错（后续脚本更新实现管理n个实例和批量管理）。
...

【主要用途】<br>
   不同运维场景下快捷使用redis-cli终端连接和切换

【免责声明】<br>
 如果对脚本不熟悉，请勿直接在生产服务器操作。待测试环境确认无误后再使用！<br>
 脚本不作代码混淆,根据自身业务场景自由扩展，测试无误后方可线上使用。<br>

【主要功能点】<br>


【目录结构】
<b>etc</b> 配置目录：<br>
<b>etc/README</b> 帮助文档<br>
<b>etc/server_list.conf</b> 管理实例配置<br>


【version 1.1.0脚本帮助说明 ( Latest Update Date: 2016-10-21)】<br>
 文档最后更新时间(Document Latest Update Date): 2016-11-01<br />

【脚本参数】<br />
-v      	: 查看脚本当前版本。<br />
-help   	: 查看帮助文档。<br />
-list   	: 查看可管理的实例列表,根据编号操作指定的redis实例。<br>
-c [Number]	: 根据编号快速选择操作的实例。<br />

        
【主要用途】<br>
        不同运维场景下快捷使用redis-cli终端快捷连接管理redis实例<br>

 【免责声明】<br>
        如果对脚本不熟悉，请勿直接在生产服务器操作。待测试环境确认无误后再使用！<br>
        脚本不作代码混淆,根据自身业务场景自由扩展，测试无误后方可线上使用。<br>

 【功能说明】<br>
        (1)满足快捷登入命令<br>
        (2)连接模式选择:<br>
        本地模式：<br>
        (HOST:127.0.0.1) <br>
        远程模式：<br>
        手动设置指定的IP和端口号<br />
        (3)配置项基本检查：
        本地模式：默认基本redis配置项提供部分通用安全配置检查(只提供基本配置项检查)
        远程模式：检查端口号配置，不提供跨服务器(考虑通用性，安全等因素，暂时不放上传此部分功能，有需要联系本人)
	验证模式: 0 宽松模式(只提示或者警告，流程继续执行) ；1 严格模式(出现错误或警告终止操作) 



 【下一版本计划】<br>
        (1).脚本状态处理<br>
        (2).分布式redis实例管理基础:<br>
        (3).日志模块:<br>
        	增加基本运维脚本操作log日志和错误日志跟踪<br>
	(4).redis实例状态指标监控<br><br><br>
 
 
 【备注】：<br />
        (1).本地配置项处理:redis.conf: <br>
        requirepass密码自动抓取到shell分析,检查密码项是否已设置,避免修改后手动设置新密码
        (2).不提供远程服务器密码自动抓取(主要出于权限和安全考虑)，只提供部分思路<br>
	
	Link: email:ceophp@163.com qq:404691073(工作常用) 1099729311 

        结束!


<br>
（平时工作比较忙，会抽空闲时间更新，邮箱或qq随时交流）<br>


