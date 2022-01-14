# redmibook 14寸本的EFI，已基本完美运行Monterey！

本人两年前在redmibook上折腾过的黑苹果，已经稳稳的运行到2022年了，本想再坚持到年中或者年底换M1的MacBookpro，无奈有些软件自己很需要但是已经更新到不能再catlina系统上运行，只好再啃啃黑苹果，试着折腾一下看看能不能升级到最新的Monterey。

结果我还是比较满意的，经过了1天多的折腾，终于算是完美的升级上来了。过程比我预想到顺利。这里需要感谢一下[fanrenkong](https://github.com/fanrenkong)大牛提供的基于big sur的Opencore版本的EFI：https://github.com/fanrenkong/Redmibook14-Big-sur。
但是他这个EFI在Monterey系统上确实不算完美，所以我在装好Monterey上针对蓝牙和音频问题有做了一些修改。最终效果还算满意，大家可以直接用我这里的EFI即可了。

简单的介绍一下我的升级过程重要的点说一下，给同样有需要的同学参考，这里最好需要有一些装黑苹果基础哈：

1. 准备镜像文件：

   从黑果小兵网站的：https://blog.daliansky.net/macOS-Monterey-12.1-21C52-Release-version-with-OC-0.7.6-CLOVER-5143-and-FirPE-original-image.html 下载带opencore的三分区安装镜像。这个安装镜像需要加微信公众号然后打赏获得，略微有些麻烦。其实理论上他网站提供的两分区的镜像版本也行，只需要把clover替换成opencore就好。

   还有一点要补充强调的就是不要再折腾clover去做引导了，据说安装新系统用OC比较好，这个我没有理论根据哈，我只是尝试用clover的时候各种卡死在启动上，实在折腾的头疼，果断放弃clover用OC了。

2. 替换掉镜像文件的EFI文件：

   这一步我的操作简单来说就是，用我提供的EFI文件，替换原黑果小兵里的EFI文件（一定是清空EFI里的文件，拷贝我提供的BOOT和OC到EFI里）。这样就能保证在你的redmibook 14本的环境下安装和运行Monterey了。

3. 安装：

   这一步我是直接在我的catlina系统上直接安装的，也就是我没有对原系统盘做个格式化而直接选择catlina所在的盘上直接安装。安装完后原来的配置和文件都在，这个是我以前没有尝试的，我觉得对原有旧黑苹果系统上升级的朋友，可以考虑这样安装，很省时省力。

以上就是我分享的主要内容了，主要还是为了那些跟我有同样升级黑苹果的朋友提供一点微薄之力。对于遇到的问题，大家可以留言，我会尽可能帮助各位。不过我还是不建议大家折腾黑苹果，过程挺折磨人的还得看运气。有这时间精力干点啥不好是不是？😄

## 电脑配置

先列一下这个电脑的配置，如果有类似配置的可以参考哈

| 设备   | 型号                                              |
| ------ | ------------------------------------------------- |
| 处理器 | Inter（R）i7-8565U 1.80Ghz                        |
| 内存   | 8Gb                                               |
| 显卡   | 1.Nvidia Geforce MX250 2.inter(R)UHD Graphics 620 |
| 硬盘   | SAMSUNG MZNLN512HAJQ 512GB                        |
| 主板   | TM814                                             |
| 声卡   | Realtek ALC256                                    |
| 网卡   | Intel Wireless-AC9462                             |
| 显示器 | NCP:4a00 分辨率 1920x1080                         |

## 完整度介绍

* 显卡：核显驱动正常
* HDMI：显示正常，但是有个小问题，就是需要进入桌面后重新插拔一下HDMI线。
* 声卡：正常。
* USB: 正常。
* 蓝牙：正常
* 电源管理：正常，可以显示剩余电量。
* wifi： 替换成博通的BCM94352Z网卡，很完美的支持系统wifi、airdrop。
* 触控板：正常，并且可以多指操作
* 功能键：本机键盘的静音键、音量+、音量-、屏幕亮度+、屏幕亮度-
* 睡眠唤醒：正常。

![](https://raw.githubusercontent.com/axap288/Redmibook-Monterey-EFI/main/sreenshot/Screenshort.png)

### 参考：

【黑果小兵】【微信首发】macOS Monterey 12.1 21C52 Installer for OpenCore 0.7.6 and CLOVER 5143 and WEPE 三 EFI 分区原版镜像：https://blog.daliansky.net/macOS-Monterey-12.1-21C52-Release-version-with-OC-0.7.6-CLOVER-5143-and-FirPE-original-image.html

fanrenkong/Redmibook14-Big-sur ：https://github.com/fanrenkong/Redmibook14-Big-sur

axap288/redmibook-catalina-efi：https://github.com/axap288/redmibook-catalina-efi

