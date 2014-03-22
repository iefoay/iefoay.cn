title: zen coding
date: 2014-02-25 14:04:04
tags:
categories:
---

meta:compat
```html
<meta http-equiv="X-UA-Compatible" content="IE=7">
```

link
```html
<link rel="stylesheet" href="">
```

link:touch
```html
<link rel="apple-touch-icon" href="favicon.png">
```

link:favicon
```html
<link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
```

link:rss
```html
<link rel="alternate" type="application/rss+xml" title="RSS" href="rss.xml">
```

script
```html
<script></script>
```

script:src
```html
<script src=""></script>
```

cc:ie6
```html
<!--[if lte IE 6]>
<![endif]-->
```

div#for-ie>cc:ie6>link+script:script
```html
<div id="for-ie">
	<!--[if lte IE 6]>
		<link rel="stylesheet" href="">
		<script:script></script:script>
	<![endif]-->
</div>
```

div#i$-test.class$$*5
```html
<div id="i1-test" class="class01"></div>
<div id="i2-test" class="class02"></div>
<div id="i3-test" class="class03"></div>
<div id="i4-test" class="class04"></div>
<div id="i5-test" class="class05"></div>
```

div#header>ul#navigation>li.item$*5>a
```html
<div id="header">
	<ul id="navigation">
		<li class="item1"><a href=""></a></li>
		<li class="item2"><a href=""></a></li>
		<li class="item3"><a href=""></a></li>
		<li class="item4"><a href=""></a></li>
		<li class="item5"><a href=""></a></li>
	</ul>
</div>
```
