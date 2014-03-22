title: 以NodeJS代码的方式使用UglifyJS2 -The hard way
date: 2013-12-30 13:53:34
tags: [UglifyJS, Node]
categories: [JavaScript]
---

本文只是作为引导入门用。详细说明请查看[官方的文档](https://github.com/mishoo/UglifyJS2#the-hard-way)
<!-- more -->
## 准备工作
- 已安装了node.js
- 有uglify-js模块

## 写NodeJS代码

创建一个名为 test.js 的文件，做为NodeJS主文件。开始写代码

```js
var UglifyJS = require("uglify-js");
```

读取源代码内容
```js
var fs = require('fs');
var orig_code = fs.readFileSync("source.js");
```

解析源代码和审查
```js
var ast = UglifyJS.parse(orig_code);
ast.figure_out_scope(); //审查。注意！这行不能省！
```

### UglifyJS.parse()
UglifyJS.parse(code, options)

*options* 是一个可选参数

- strict
- filename
- toplevel


对源代码进行压缩
```js
var compressor = UglifyJS.Compressor({//Compressor options
	join_vars: true
});
ast = ast.transform(compressor);
```

[*Compressor options*](https://github.com/mishoo/UglifyJS2#compressor-options)

- join_vars
- properties
- conditionals
- ...

下面的操作，根据自己的需要调用
```js 
ast.figure_out_scope(); //再检查没用的代码
ast.mangle_names(); //压缩名称
```

### 输出

*方式1（较简单）*

```js
var final_code = ast.print_to_string({//Beautifier options
    beautify: true
});
```

*方式2（较啰嗦）*

```js
var stream = UglifyJS.OutputStream({//Beautifier options
    beautify: true
});
ast.print(stream);
var final_code = stream.toString();
```

[*Beautifier options*](https://github.com/mishoo/UglifyJS2#beautifier-options)

- beautify
- indent-level
- indent-start
- ...

### 输出到文件

输出到项目目录下的 output.min.js 文件
```js
fs.writeFileSync("output.min.js", orig_code);
```