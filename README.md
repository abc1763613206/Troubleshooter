# Troubleshooter
一个关于Magisk和Android的Troubleshooter，来自于QQ群@698016310

# 0x01 刷机
### 1.选一台好的手机
你的搞机之路能否成功，和你的`手机型号`和`手机操作系统类型`有关，一般小米（MIUI）会比较好搞些，三星索尼相反。  
*（其实一代神机`红米Note4X`最适合搞机了）*


# FAQ
```
如有引用酷安链接可去参考链接自行查看！
```
#### 1.装了magisk怎么正常ota啊
官方rec进行ota操作  
magisk工作方式通过拦截隐藏源文件，然后进行替换！而源文件还在  
通过这个原理，那么我们就可以用Magisk来改系统了，系统ota验证一般安卓目录分区，还有内核，我们一般动也是动这两分区  
1：最简单的方法就是，软件内点击卸载还原boot分区，然后关机就能ota了  
2：进入`/data/stock_boot_85f6e87d9f00375e612f51267cd8db94b0fab263.img.gz`，把这个gz解压出来，会有一个boot，rec刷入boot，就能ota了，ota后再刷入Magisk就行了  

第三方rec进行ota，直接高级设置打开支持ota  
这种方法是采用本地备份法备份官方ROM，当检测到ota刷机包的时候，会直接恢复本地备份的ROM，然后ota，这个不管你怎么改，都能ota  


#### 2.状态栏怎么自己改？现在miui9.5用群文件的主题破解用第三方mtz会卡主题…
稳定版暂时不适配主题破解，直接用xp试试主题破解，关于状态栏教程，后期关注我酷安id就行了
#### 3.主系统听音乐没有声音，玩游戏有。副系统有声音，怎么解决
主系统ROM本身有问题，无法解决，换ROM  
#### 4.主系统怎么弄面具，但和supersu产生冲突。那supersu怎么从主系统彻底删除
还原boot分区/重刷一遍不带SU的ROM  
#### 5.安装了面具会加密data分区。那副系统是不是用不了，如果用不了该怎么解决
面具不会加密data分区，主系统不升级，自然不会加密  
#### 6.能说一下市面主流手机刷机的一般步骤吗？
rec刷机模式:  
傻瓜式:申请解锁帐号→bl/fb解锁→奇兔一键刷机(获取rec)→下载刷机包刷入就行了  
线刷模式:线刷包自带教程   
9008还原救砖模式  
#### 7.我的magisk安装失败，该如何排查？
如果是面具本身安装失败，一般都是内核问题，还原boot分区就行  
关于排查:英文提示翻译成中文，自己自然可以理解
#### 8.推荐一些好的模块呗/我想省电/养老/黑科技，选什么操作系统好？（原生/类原生/官改/MIUI）
一千个读者，就有一千个哈姆雷特，众口难调，没有好的模块，只有自己需要的，适合的
#### 9.我的手机刷了Magisk/Xposed后经常FC，怎么办？
手机不兼容，推荐换ROM版本
#### 10.能讲讲Magisk和Xposed的区别吗？
①xp框架的模块是通过查找原软件的代码，进行拦截，然后释放自身模块的代码到进程内，工作环境是进程，这也就是为何有些软件升级失效，因为进程代码被改了，通过拦截代替达不到效果！  
②Magisk框架的模块是通过查找安卓文件目录的文件，进行拦截，然后释放自身模块的文件到安卓目录下，工作环境是安卓目录  
③他们相同的工作方式通过拦截隐藏源文件，然后进行替换！而源文件还在  
`magisk和xp互不干涉，magisk里的xp提取是xp官方的，一点都没改，官方有什么bug，magisk也不会少！  `
#### 11.我想要个顺手的机子，推荐一台适合搞机的手机吧？
小米4/高通骁龙处理器的手机，都适合搞机
#### 12.我想研究下Magisk的模块，除了酷安和MIUI论坛外，还有什么交流的地方？
[xda-developers](http://forum.xda-developers.com/)  
#### 13.我知道一些好的刷机包，该如何制作Magisk模块和卸载包？
刷机包制作不了，补丁包才有可能运，制作教程直接用万能模板，这是酷安傻瓜式教程：https://www.coolapk.com/feed/6056739  
#### 14.刷什么样的内核好？如果翻车了如何解决？
内核还是官方好，毕竟原配是最好的，翻车了刷机解决  
#### 15.我想在xda上搜寻模块，该如何查找？应避免哪些问题？
看的懂英文就行了，看不懂再解释也无用  
https://www.coolapk.com/feed/5699638 
#### 13.Magisk和Xposed中的模块冲突吗？如果真冲突了如何解决？
#### 14.Magisk模块和本体安装报错，如何排解问题？
#### 15.装了Magisk后死活过不了SafetyNet，怎么破？
#### 16.如果安装Xposed/Magisk模块后应用FC输出了日志，该如何排查问题？
#### 17.除了Magisk和Xposed，还有什么好用的框架？
#### 18.偶然得到了一个刷机包，该如何检验它是否有危害？


# 参考文献
## 来自酷安@潇风残月
### https://www.coolapk.com/feed/5709010
```
本帖分4个板块:  
①Magisk的安装教程②Magisk常见问题解决和功能介绍  
③Magisk的模块制作④Magisk维护和升级  
前言:很多人有误解，xp和框架和Magisk是不是一类的？工作修改原理是差不多的，但是工作目录路径不同，简言之：  
①xp框架的模块是通过查找原软件的进程代码，进行拦截，然后释放自身模块的代码到进程内，工作环境是进程，这也就是为何有些软件升级失效，因为进程代码被改了，通过拦截代替达不到效果！  
②Magisk框架的模块是通过查找安卓文件目录的文件，进行拦截，然后释放自身模块的文件到安卓目录下，工作环境是安卓目录  
③他们相同的工作方式通过拦截隐藏源文件，然后进行替换！而源文件还在  
④Magisk和xp互不干涉，Magisk里的xp提取的是xp官方的，一点都没改，官方有什么bug，magisk也不会少！  
④关于卡米，卡开机，官方开机一般会验证boot内核，请刷入支持关闭boot验证的rec关闭就行  
⑤如果真要说Magisk和xp的关系，那只能说Magisk是xp的入口，有Magisk可以刷xp，但是有xp不能刷Magisk，Magisk可以提供xp框架的接口  
⑥既然如此，那么比如要修改某款软件，达到去广告，或者美化效果，通过xp框架和Magisk实现，有何不同呢？例如状态栏美化，  
xp框架拦截状态栏进程代码释放自身代码，理论通用  
Magisk的状态栏美化是通过替换状态栏文件修改的，所以不通用  
Magisk修改偏专用性（修改不影响卡顿），xp修改偏通用性（修改会影响卡顿）  

前言结束  
```
正文  
①Magisk的安装引用@某炎子大佬的帖子
另外自己补充一下，Magisk不局限运用于MIUI，基本通吃安卓，上至8.1，下至5.0  
如果之前是SU，如何安装Magisk？  
关于SUroot如何变成magiskroot，有两种方案  
1：成功率★★★★：提取官方boot刷入，然后刷入magisk  
2：成功率★★：先刷入magisv12版本，Magisk是不会管内核的，强制刷入，然后安装4.3.1magisk管理器，然后再进入模块那里，选择安装模块，magiskv16.0就行，重启把magisk升级最新版，再次安装magiskv16.0，SU成功被接管了  
②常见问题解决（图1）  
1：刷入Magisk如果出现  
```
Device platform: arm64  
Extracting files  
Patch boot/ramdisk image: /dev/block/mmcblk0p21  
Unpacking boot image  
Checking ramdisk status  
Boot image patched by other programs  
Please restore stock boot image  
Failed!  
!Installation failed  
```
▲那么可以用正文①②的方式安装  
2刷入模块如果出现（图2+图3）  
```  
Please install Magisk v15.0+!  
Failed!  
!Installation failed  
```
▲那么意思就是Magisk底层版本需要v15.0+才能刷入，同理如果是Please install Magisk v16.0+!，就要Magisk v16.0+底层  
3：不管刷什么模块，都是显示失败，然后提示保存到内部存储（图2+图3）  
▲那么你就要进入/data/magisk.img查看这个文件是否存在，如果不存在，那就是需要重新刷入Magisk解决，或者把强制加密关了，有可能/data/magisk.img分区无法进行读写  
4：双清会不会丢Magisk的root？  
▲Magisk root是通过修改boot分区实现的，所以双清不改变boot分区，不会，由于/data/magisk.img是在data分区，所以模块会全部丢失，需要重刷一遍Magisk激活img分区才能使用模块安装功能  
5：关于magisk hide 的使用方法  
▲用于屏蔽其他软件检测root权限，使用magisk hide 勾选重启，清除该应用数据然后打开它就行了  
关于Magisk的安装教程和Magisk常见问题解决和功能介绍我们就谈到这里了，我们下期再见  
下期预测  
③Magisk的模块制作：制作出自己专属的模块，加入版权（图4+图5）  
④Magisk维护和升级：模块的升级，模块的维护，模块的修改（下期预测！）  
一些仓库找不到的个人觉得比较好的模块：链接: https://pan.baidu.com/s/1dowJQe  密码:2o52  
### https://www.coolapk.com/feed/6056739
```
本帖分4个板块:  
①Magisk的安装教程②Magisk常见问题解决和功能介绍  
③Magisk的模块制作④Magisk维护和升级  
前言: https://www.coolapk.com/feed/5709010 教程1  

xp框架拦截状态栏进程代码释放自身代码，理论通用  
Magisk的状态栏美化是通过替换状态栏文件修改的，所以不通用  
Magisk修改偏专用性（修改不影响卡顿），xp修改偏通用性（修改会影响卡顿）  
`正是由于专用性，适配性，且国内手机系统五花八门，导致Magisk模块少之又少，好在Magisk模块的制作方法不是很难，普通模块不需要代码技术  `

本期就简单说说模块的制作  
```
正文  
①首先讲下magisk模块的基本结构！如图1  

META-INF文件夹、system文件夹、config.sh文件、module.prop文件   
至于我没有写出来的，都是附属品，可有可无，要懂代码脚本才能去写去改  
META-INF文件夹是签名文件夹和刷机界面的提示（无需更改）  
system文件夹，映射根目录/system/  
config.sh安装模块处理文件并修改magisk.img（无需更改）  
module.prop文件，模块的一些备注信息  
②刷机包转化为模块  
既然Magirk中的system文件夹，是映射根目录/system/，所以也就是说跟刷机包差不多  
转化例子：如图2  
  
1、解压你要转化的刷机包，获得META-INF文件夹和system文件夹  
2、下载并解压Magisk万能模板（已升级内核版本为16.0）  
Magisk-万能通用模板，核心底层v16.zip  
https://pan.baidu.com/s/12d1AwMinIt3l4_U7o5bOAA   
3、删除1步骤的META-INF文件夹，删除2步骤的system文件夹，然后将1步骤的system文件夹复制/剪切黏贴到2步骤中  
4、打开module.prop文件进行编辑，例如如图3  
```  
id=MiuiPro（映射文件夹名称，不能用空格，不能有空格符，随便取名称，就好比编号一样）  
name=MIUI高级设置（模块信息名称）  
version=v8.8稳定版（模块版本）  
versionCode=1（无）  
author=小白杨（作者信息）  
description=①完善系统文件碎片化（介绍）  
minMagisk=1600（最低兼容面具版本，1600=MagiskV16，一般别去改，如果跟内核底层不一致，很容易模块报废无法识别，除非模块一直刷入报错）  
```
③模块自制，制作思路跟卡刷包差不多  
解压获得万能模板，然后在system文件夹扔入该修改的文件，利用映射方法拦截覆盖就行了  
  
★★教程一和教程二隔了这么久没更新，主要是楼主最近有点抑郁，所以没啥心情更新  
当然，如果你要做出好的模板，代码肯定要学会的  
我们下期再见！  
Magisk模块归总：链接: https://pan.baidu.com/s/1qooAL5a5lqJ2g_BYm0iHIA  密码:9776  
高级设置v8.8正式版：链接: https://pan.baidu.com/s/1oXSh1Dc2_kQI70l11tONFA  密码:m4r6  
MIUI精简自带root包：链接: https://pan.baidu.com/s/1SDBYjD2Ru3TSyKnpLnsGNA  密码:839c  
### https://www.coolapk.com/feed/5699638
```
很多人一谈英语就头疼，比如楼主，中考成绩进前三，就是英语拖后腿了，每次模拟考试就期待英语要难，唯一一次班排第一还是英语试卷范围超过了我们所学的知识点，然后那题目又出的刁钻古怪，导致我跟第二名英语成绩只有20几分的差距，高中英语就更别提了，及格掰着手指头都能数清楚
但是我却对搞机情有独钟，有人说把手机系统语言设置英文，我觉得没啥用，我有强迫症，受不了一大堆的英文，而且也看不懂，当然，我们也不会为了搞机，特意去像学习那样学习英语，什么四六级，不存在的，那么有什么好的建议么？（望文生意）
```
就好比相信很多人进英文网站下载资源，通篇只会找download！  
看不懂英文句子不要紧，但是我们总不至于单词都不认识吧，必学单词:   
1:setting（设置），例如xx setting，就知道是xx设置了，那么xx就是我们要提取的关键词，提取出来了，就可以用翻译软件翻译  
2关于日志如何查找关键词，请牢记Please（请）:例如  
请升级最新版，请获取root权限，请干什么，都是给了原因  
下面给一段英文：  
```
Device platform: arm64
Extracting files
Patch boot/ramdisk image: /dev/block/mmcblk0p21
Unpacking boot image
Checking ramdisk status
Boot image patched by other programs
Please restore stock boot image
Failed!
!Installation failed
```
通篇只需查找两个关键词：failed（失败）这是结果  
原因呢？Please，所以这段就是我们要的：Please restore stock boot image（翻译：请恢复原始镜像）  
restore stock boot image这段我们就可以用翻译软件来翻译，是不是比通篇翻译容易呢？  
3：download（下载），进入一个网页下载东西，其余问题对于我们来说都是废话，所以只找download  
4：install（安装），例如xp install/install xp（安装xp）  
un，通常表示否定，否定理解就是反义词了，那么安装的反义词就是卸载，uninstall（卸载），xp uninstall/uninstall xp（卸载xp）  
5：app（软件）这个不解释  
说了这么多，想搞机，就要多学习，多动手，配合翻译软件，xp有xp快译，输入法有百度搜狗，网站有百度搜狗，浏览器都自带了！  
一些实用的magisk模块和xp模块：  
链接: https://pan.baidu.com/s/1gggfbhD  密码:ui18  

