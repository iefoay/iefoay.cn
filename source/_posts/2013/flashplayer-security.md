title: Flash Player 全局安全设置
date: 2013-12-19
tags: [flash, flashplayer, 安全, 本地]
categories: [flash]
---

我们在本地环境测试flash内容时，由于受到了安全沙箱限制，flash以下行为可能会受阻。通过添加信任位置，可通过此限制。

- 请求远程接口
- 调用HTML接口


<p id="flashinfo"></p>
<script type="text/javascript">var a=swfobject.ua.pv;if(a[0]){var info=a[0];}else{info='<b>此浏览器居然没有安装 Flash Player插件！！</b>';}$('<strong>此浏览器使用的 Flash Player 版本：'+a.join('.')+'</strong>').appendTo('#flashinfo');</script>

## 开始设置

在任意一个 Flash Player 区域中，点击右键 - **全局设置**。注意：由于不同的 Flash Player 版本，会有两种不同的情况出现。
<!-- more -->

0. 跳转到 [官方的设置页](http://www.macromedia.com/support/documentation/cn/flashplayer/help/settings_manager04.html)
0. 弹出 **Flash Player 设置管理器** 面板

根据自己的出现的情况查看下面的图解即可

## 通过官方的设置页

此页面在国内访问可能有点慢，耐心等待一下。右边有个设置管理器面板，是flash内容，如果没安装插件会提示你安装。

0. 确认自己在 **“全局安全设置”面板** 的标签。
![网页](http://iefoay.cn/img/flashplayer/flashplayer_web1.png)

0. 这里有个列表，表示已经在本机添加过的位置。点击 **编辑多个位置** 右边的下拉三角，选择 **添加位置**
![设置面板](http://iefoay.cn/img/flashplayer/flashplayer_web2.png)

0. 选择 **浏览文件夹** ，在弹出本地窗口选择要查看的swf文件所在目录或其父级目录。
![设置面板](http://iefoay.cn/img/flashplayer/flashplayer_web3.png)

0. 看到信任位置已经添加成功。

0. 刷新刚才的包涵flash的页面。


## 通过 Flash Player 设置管理器

0. 点击 **高级** 标签。找到 **受信任位置设置** ，在稍下面的位置，可能需要一下滚动条才能看到 :)
![设置面板](http://iefoay.cn/img/flashplayer/flashplayer_1.png)

0. 这里有个列表，表示已经在本机添加过的位置。点击 **添加**
![设置面板](http://iefoay.cn/img/flashplayer/flashplayer_2.png)

0. 选择 **添加文件夹** ，在弹出本地窗口选择要查看的swf文件所在目录或其父级目录。
![设置面板](http://iefoay.cn/img/flashplayer/flashplayer_3.png)

0. 看到信任位置已经添加成功。

0. 刷新刚才的包涵flash的页面。
