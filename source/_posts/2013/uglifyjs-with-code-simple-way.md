title: 以NodeJS代码的方式使用UglifyJS2 -The simple way
date: 2013-12-30 13:55:00
tags: [UglifyJS, Node]
categories: [JavaScript]
---

UglifyJS 是一个 JavaScript 的打包、压缩工具。建议使用第2个版：UglifyJS2，详情见[Github](https://github.com/mishoo/UglifyJS2)。
一般来说，使用简单的方式，就能满足我们的需求。

<!-- more -->
## 安装

这里使用 *命令行* 的方式安装 UglifyJS2。其实就是把 *uglify-js* 模块下载到你的当前目录。
```
cd your/project/path
npm install uglify-js
```

## 写NodeJS代码

创建一个名为 test.js 的文件，做为NodeJS主文件。开始写代码。

```js
var UglifyJS = require("uglify-js");
var result = UglifyJS.minify("source.js");
console.log(result.code);
```

切换到*使命行*，看看输出结果
```
node test.js
```

## 方法说明

### UglifyJS.minify()

UglifyJS.minify(input, option)

**参数**

名称	|	类型		|	必选	|	说明
-|
input	|String &#124; Array|	是	|	输入，可以是文件路径，也可以是源代码的字符串
option	|	Object		|		否	|	综合选项

*option*
```js option 参考配置表
{
	fromString: true,		//说明代码源的格式是否为字符串
	mangle: false,			//是否压缩
	warnings: false,			//显示压缩报错
	output: {
		beautify: false,		//代码格式美化，便于阅读
		comments: false	//是否保留注释
		...
	},
	compress: {
		global_defs: {},		//定义全局变量
		join_vars: true		//使用连贯的变量声明
		...
	}
}
```

可以组合多个文件：
```js
var result = UglifyJS.minify([ "file1.js", "file2.js", "file3.js" ]);
```

代码源也可以是字符串：
```js
var orig_code = "var abc = 1;";
var result = UglifyJS.minify(orig_code, {
	fromString: true
});
```
