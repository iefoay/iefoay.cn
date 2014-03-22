title: 使用 SWFObject 嵌入 flash 内容
date: 2013-12-23
tags: [flash]
categories: [flash]
---

## 下载

[swfobject_2_2.zip](http://iefoay.cn/downloads/swfobject_2_2.zip)

## 从一个最简单的例子开始

### 
```html 第一步：创建一个标签，将被替换为flash内容
<div id="myContent"></div>
```
<!-- more -->
### 
```html 第二步：导入swfbject.js库
<script type="text/javascript" src="swfobject.js"></script>
```
### 
```html 第三步：使用 swfobject.embedSWF 方法嵌入flash文件
<script type="text/javascript">
	swfobject.embedSWF("myContent.swf", "myContent", "300", "120", "9.0.0");
</script>
```

整体结果：
```
<!DOCTYPE html>
<html>
<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<title>SWFObject 动态嵌入</title>
	<script type="text/javascript" src="swfobject.js"></script>
	<script type="text/javascript">
		swfobject.embedSWF("myContent.swf", "myContent", "300", "120", "9.0.0");
	</script>
</head>
<body>
	<div id="myContent"></div>
</body>
</html>
```

## 方法

### swfobject.embedSWF()
swfobject.embedSWF(swfUrl, replaceElementId, width, height, version, expressInstallSwfurl, flashvars, params, attributes, callbackFn)

更详细和列全面的了解一下，`swfobject.embedSWF`方法就是用来嵌入swf的

**参数**

名称				|	类型	|	必选	|	说明
-|
swfUrl				|	String	|	是		|	swf文件路径，即：嵌入谁
replaceElementId	|	String	|	是		|	将被替换为flash内容的标签，即：嵌入到哪
width				|	String	|	是		|	flash区域的宽
height				|	String	|	是		|	flash区域的高
version				|	String	|	是		|	所需要的 Flash Player 插件的最低版本
expressInstallSwfurl|	String	|	否		|	用于帮助用户更新 Flash Player 
flashvars			|	Object	|	否		|	为flash提供参数
params				|	Object	|	否		|	flash对象的嵌入方式
attributes			|	Object	|	否		|	给flash对象设置属性，如：指定id
callbackFn			|	Function|	否		|	回调函数，嵌入完成（包括失败）将被调用


*params*

- **menu**= false | true --在flash区域内的右键菜单中，是否显示控制动画相关选项
- **wmode**= **window** | direct | opaque | transparent | gpu
- **bgcolor** --背景颜色，格式：#RRGGBB
- **base** --目录
- **allowFullscreen**= **false** | true
- **allowScriptAccess**= **samedomain** | never | always
- **play**= false | **true**
- **loop**= false | **true**
- **quality**= low | autolow | autohigh | medium | high | best
- **scale**= **showall** | noborder | exactfit | noscale
- **align**= l | t | r --参数分别代表left、top、right
- **salign**= l | t | r | tl | tr --参数分别代表left、top、right、topleft、topright

*attributes*

如需要用js访问flash对象时，为了浏览器兼容性，**id** 和 **name** 两个属性都应该设置，且用同样的值

### 最终结果：
```
<!DOCTYPE html>
<html>
<head>
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
	<title>SWFObject 动态嵌入</title>
	<script type="text/javascript" src="swfobject.js"></script>
	<script type="text/javascript">
		var flashvars = {
			name1: "hello",
			name2: "world",
			name3: "foobar"
		};
		var params = {
			menu: "false",
			wmode: "direct"
		};
		var attributes = {
			id: "myDynamicContent",
			name: "myDynamicContent"
		};
		swfobject.embedSWF("myContent.swf", "myContent", "300", "120", "9.0.0",
			"expressInstall.swf",
			flashvars,
			params,
			attributes
		};
	</script>
</head>
<body>
	<div id="myContent"></div>
</body>
</html>
```

## 参考
官方首页：<http://code.google.com/p/swfobject/>
帮助文档：<http://code.google.com/p/swfobject/wiki/documentation>
API文档：<http://code.google.com/p/swfobject/wiki/api>
