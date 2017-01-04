<h2>HTML和CSS的格式和代码规范，提高代码质量和协作效率</h2>
<h4>通用样式规范</h4>
<h5>协议</h5>
省略图片/样式/脚本及其它媒体文件URL的协议部分（http:,https:）,除非文件在两种协议下都不可用。这种方案称为protocol-relative URL,好处是无论你是使用HTTPS还是HTTP访问页面,浏览器都会以相同的协议请求页面中的资源,同时可以节省一部分字节。
```
<!-- Not recommended -->
<script src="https://www.google.com/js/gweb/analytics/autotrack.js"></script>
```
```
<!-- Recommended -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js">
```
```
/* Not recommended */
.example {
  background: url("https://www.google.com/images/example");
}
```
```
/* Recommended */
.example {
  background: url("//www.google.com/images/example");
}
```
<h4>通用格式规范</h4>
<h5>缩进</h5>
一次缩进2个空格，不要使用tab或者混合tab和空格的缩进。
```
<ul>
  <li>One</li>
  <li>Two</li>
</ul>
```
```
.example {
  color: red;
}
```
<h5>大小写</h5>
以下都应该用小写：HTML元素名称，属性，属性值（除非text/CDATA），CSS选择器，属性，属性值。
```
<!-- Not recommended -->
<A HREF="/">Home</A>
```
```
<!-- Recommended -->
<img src="google.png" alt="Google">
```
```
/* Not recommended */
color: #F2F2F2;
```
```
/* Recommended */
color: #f2f2f2;
```
<h5>结尾空格</h5>
结尾空格不仅多余，而且在比较代码时会比较麻烦。
```
<!-- Not recommended -->
<p>What?_ </p>
```
```
<!-- Recommended -->
<p>What?</p>
```
<h4>通用元规则</h4>
<h5>编码</h5>
在HTML中通过`<meta charset="utf-8">`指定编码方式，CSS中不需要指定，因为默认为UTF-8。
<h5>注释</h5>
使用注释来解释代码：包括的模块，功能以及优点。
<h5>任务项</h5>
用TODO来标记待办事项，而不是用一些其它的标记，如@@。
```
<!-- TODO: remove optional tags -->
<ul>
  <li>Apples</li>
  <li>Oranges</li>
</ul>
```
<h4>HTML风格规范</h4>
<h5>文档类型</h5>
HTML文档应使用HTML5的文档类型`<!DOCTYPE html>`
孤立标签无需封闭自身， `<br>`不要写成 `<br />`。
<h5>HTML正确性</h5>
尽可能使用正确的HTML。
```
<!-- Not recommended -->
<title>Test</title>
<article>This is only a test.
```
```
<!-- Recommended -->
<!DOCTYPE html>
<meta charset="utf-8">
<title>Tetst</title>
<article>This is only a test.</alticle>
```
<h5>语义化</h5>
根据使用场景选择正确的HTML元素（有时被错误的称为"标签"）。例如，使用h1元素创建标题，p元素创建段落，a元素创建链接等等。正确的使用HTML元素对于可访问性／可重用醒以及编码效率都很重要。
```
<!-- Not recommended -->
<div onclick="goToRecommendations();">All recommendations</div>
```
```
<!-- Recommended -->
<a href="recommendations/">All recommendations</a>
```
<h5>多媒体元素降级</h5>
对于像图片／视频／canvas动画等多媒体元素，确保提供其他可访问的内容。图片可以使用替代文本（alt），视频和音频可以使用文字版本。
```
<!-- Not recomended -->
<img src="spreadsheet.png">
```
```
<!-- Recomended -->
<img src="apreadsheet.png" lit="Spreadsheet screenshot.">
```
<h5>关于分离</h5>
标记／样式和脚步分离，确保相互耦合最小。
<h5>实体引用</h5>
如果团队中文件和编辑器使用同样的编码方式，就没用必要使用实体引用，如&mdash;,&rdquo;,&#x263a;,除了一些在HTML中有特殊含义的字符（如<和&）以及不可见的字符（如空格）。
```
<!-- Not recommended -->
The currency symbol for the Euro is &ldquo;&eur;&rdquo;
```
```
<!-- Recommended -->
The currency symbol for the Euro is “€”.
```
<h5>type属性</h5>
在引用样式表和脚本时，不要指定type属性，除非不是CSS或JavaScript。因为HTML5中已经默认指定样式变的type是text/css，脚本的type是text/javascript。
```
<!-- Not recommended -->
<link rel="stylesheet" href="//www.google.com/css/main.css" type="text/css">
```
```
<!-- Recommended -->
<link rel="stylesheet" href="//www.google.com/css/main.css">
```
```
<!-- Not recommended -->
<script src="//www.google.com/js/main.js" type="text/javascript"></script>
```
```
<!-- Recommended -->
<script src="//www.google.com/js/main.js"></script>
```
<h4>HTML格式规范</h4>
<h5>HTML引号</h5>
属性值使用双引号。
```
<!-- Not Recomended -->
<a class='main-button main-button-blue'>Sign in</a>
```
```
<!-- Recommended -->
<a class="main-button main-button-blue">Sign in</a>
```
<h4>CSS风格规范</h4>
<h5>ID和Class命名</h5>
使用有含义的id和class
```
/* Not recommended: meaningless */#yee-1901 {}/* Not recommended: presentational */
.button-green {}
.clear {}
```
```
/* Recommended: specific */#gallery {}#login {}.video {}

/* Recommended: generic */
.aux {}
.alt {}
```
<h5>ID 和 Class 命名风格</h5>
id 和 class 应该尽量简短，同时要容易理解。
```
/* Not recommended */#navigation {}.atr {}
```
```
/* Recommended */#nav {}.author {}
```
<h5>选择器</h5>
除非需要，否则不要在 id 或 class 前加元素名。
```
ul#example {}div.error {}
```
```
/* Recommended */#example {}.error {}
```
<h5>属性简写</h5>
尽量使用 CSS 中可以简写的属性 (如 font)，可以提高编码效率以及代码可读性。
```
/* Not recommended */
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```
```
/* Recommended */
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```
<h5>0 和单位</h5>
值为 0 时不用添加单位。
```
margin: 0;
padding: 0;
```
<h5>开头的 0</h5>
值在 -1 和 1 之间时，不需要加 0。
```
font-size: .8em;
```
<h5>16进制表示法</h5>
除非需要，否则不要在 id 或 class 前加元素名。
```
/* Not recommended */
color: #eebbcc;
```
```
/* Recommended */
color: #ebc;
```
<h5>前缀</h5>
使用带前缀的命名空间可以防止命名冲突，同时提高代码可维护性。
```
.adw-help {} /* AdWords */#maia-note {} /* Maia */
```
<h5>ID 和 Class 命名分隔符</h5>
选择器中使用连字符可以提高可读性。
```
/* Not recommended: does not separate the words “demo” and “image” */
.demoimage {}

/* Not recommended: uses underscore instead of hyphen */
.error_status {}
```
```
/* Recommended */#video-id {}.ads-sample {}
```
<h4>CSS格式规范</h4>
<h5>书写顺序</h5>
按照属性首字母顺序书写 CSS 易于阅读和维护，排序时忽略带有浏览器前缀的属性。
```
background: fuchsia;
border: 1px solid;
-moz-border-radius: 4px;
-webkit-border-radius: 4px;
border-radius: 4px;
color: black;
text-align: center;
text-indent: 2em;
```
<h5>块级内容缩进</h5>
为了反映层级关系和提高可读性，块级内容都应缩进。
```
@media screen, projection {

  html {
    background: #fff;
    color: #444;
  }

}
```
<h5>声明结束</h5>
每行 CSS 都应以分号结尾。
```
/* Not recommended */
.test {
  display: block;
  height: 100px
}
```
```
/* Recommended */
.test {
  display: block;
  height: 100px;
}
```
<h5>属性名结尾</h5>
属性名和值之间都应有一个空格。
```
/* Not recommended */
h3 {
  font-weight:bold;
}
```
```
/* Recommended */
h3 {
  font-weight: bold;
}
```
<h5>声明样式块的分隔</h5>
在选择器和 {} 之间用空格隔开。
```
/* Not recommended: missing space */#video{
  margin-top: 1em;
}

/* Not recommended: unnecessary line break */#video{
  margin-top: 1em;
}
```
```
/* Recommended */#video {
  margin-top: 1em;
}
```
<h5>选择器分隔</h5>
每个选择器都另起一行。
```
/* Not recommended */
a:focus, a:active {
  position: relative; top: 1px;
}
```
```
/* Recommended */
h1,
h2,
h3 {
  font-weight: normal;
  line-height: 1.2;
}
```
<h5>规则分隔</h5>
规则之间都用空行隔开。
```
html {
  background: #fff;}

body {
  margin: auto;
  width: 50%;
}
```
<h5>CSS 引号</h5>
属性选择器和属性值用单引号，URI 的值不需要引号。
```
/* Not recommended */@import url("//www.google.com/css/maia.css");html {
  font-family: "open sans", arial, sans-serif;
}
```
```
/* Recommended */@import url(//www.google.com/css/maia.css);html {
  font-family: 'open sans', arial, sans-serif;
}
```
<h4>CSS元规则</h4>
<h5>分段注释</h5>
用注释把 CSS 分成各个部分。
```
/* Header */#adw-header {}/* Footer */#adw-footer {}/* Gallery */

.adw-gallery {}
```
<h4>结语</h4>
坚持遵循代码规范。

写代码前先看看周围同事的代码，然后决定代码风格。

代码规范的意义在于提供一个参照物。这里提供了一份全局的规范，但是你也得参照公司内部的规范，否则阅读你代码的人会很痛苦。