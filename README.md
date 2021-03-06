# 效果图

![](https://raw.githubusercontent.com/chenfanfang/WeChatRedPacket/master/snapshot/redPacket.png)


# 注:
本项目主要目的是用来学习逆向知识，可以很好地使用xcode来进行编码，有了xcode的代码提示帮助，大大提高了逆向编码效率，并且由于MonkeyDev的自动化，省去了动态库注入和签名的流程。

由于微信的检测机制，是存在账号被封的危险。若实在想用抢红包功能，建议对使用越狱手机，并且使用Theos创建tweak项目,并且将本文项目的objc-class文件夹中的所有类、Logos文件夹中的WeChatRedPacketDylib.xm 拷贝到tweak项目中进行打包和安装到越狱机中即可。

本文项目是基于开源项目WeChatRedEnvelop进行小修改完成

# 项目运行步骤

##### 1、搭建运行环境
使用前，需要先搭建MonkeyDev,具体搭建方法请看[官方教程](https://github.com/AloneMonkey/MonkeyDev/wiki/%E5%AE%89%E8%A3%85)
环境搭建好即可直接使用xcode运行本项目

##### 2、导入脱壳的微信ipa包
将脱壳的微信的ipa包命名成全英文``` 例如:WeChat.ipa```,并且复制到/WeChatRedPacket/WeChatRedPacket/TargetApp文件夹中

##### 3、配置好基本配置
>1、【修改Bundle Identifier】微信自身的Bundle Identifier为：com.tencent.xin,可以取一个不一样的Bundle Identifier既可与原来的微信共存，即所说的微信多开。
>
>2、【修改Display Name】可以给应用重新命名：例如：微信1
>
>3、【配置好证书】



##### 4、运行
>1、配置好上面步骤，就可以直接用xcode直接运行项目了，必须使用真机哦，不可以使用模拟器【打包步骤请查看MonkeyDev的打包步骤】
>
>2、若运行报 Failed to locate Logos Processor. Is Theos installed?的错误，具体错误请看下图。若报错，请看```步骤5```
>
![](https://raw.githubusercontent.com/chenfanfang/WeChatRedPacket/master/snapshot/Theos_Error.png)



##### 5、解决Theos问题的报错

>1、若步骤4、运行已经可以正常运行项目，请忽略这个步骤
>
2、请确保MonkeyDev环境是否正常搭建，若正常搭建，请修改如下两个地方
>>1、找到 WeChatRedPacketDylib-Prefix文件，将#import "/opt/theos/Prefix.pch"中的```/opt/theos```改成你theos装在电脑中的绝对路径，比如我theos所安装的路径为/Users/chenfanfang/dev/ios_jailbreak_environment/tools/theos,则改完后的为
>>```#import "/Users/chenfanfang/dev/ios_jailbreak_environment/tools/theos/Prefix.pch"```
>>
>>2、项目target选择WeChatRedPacketDylib、选中Build Settings、滑动到最底部、将MonkeyDevTheosPath的路径改成你电脑中theos所安装的绝对路径，比如我theos所安装的路径为
>>/Users/chenfanfang/dev/ios_jailbreak_environment/tools/theos，则直接改成
>> /Users/chenfanfang/dev/ios_jailbreak_environment/tools/theos即可，
>> 具体请看下图所示
>> ![](https://raw.githubusercontent.com/chenfanfang/WeChatRedPacket/master/snapshot/MonkeyDevTheosPath.png)
>> 
>> 3、重新使用xcode运行项目即可启动

