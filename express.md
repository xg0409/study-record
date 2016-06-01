#express
Express团队维护了一个可以快速生成项目模板的可执行文件,如果你使用npm全局安装的express-generator, 在你的机器任何位置它都是可用的
<pre>
  npm install -g express-generator
</pre>
这个工具提供了一个非常简单的生成一个程序骨架的功能，但是它也有局限，比如它只支持很少的几个模板引擎
<pre>
Usage: express [options]

Options:

  -h, --help          输出帮助信息
  -V, --version       输出版本号
  -e, --ejs           添加 ejs 模板引擎支持 (默认为jade)
  -H, --hogan         添加 hogan.js模板引擎支持
  -c, --css   样式 <引擎> 支持 (less|stylus) (默认为css)
  -f, --force         强制在非空目录执行
</pre>

#Express框架中如何引用ejs模板引擎

在NodeJS指南中利用利用以下命令建立网站的基本结构：

express -t ejs microblog

运行这个命令后继续运行

cd microblog && npm install（安装项目的依赖属性），

发现安装的模板引擎是jade，而不是ejs。原因是现在的版本已经没有-t这个命令了，改为

express -e  microblog

运行完这个命令，继续运行cd microblog && npm install，ejs模板引擎就安装好了

但是express3以上的版本把layout默认给取消了，所以现在在views文件夹下并没有生成layout.ejs。

2.安装了ejs后，如何使用ejs的layout模板 

   安装express-partials

    在cmd中切换到项目目录，运行npm install express-partials或者

   在 package.json 里面的 dependencies 添加 "express-partials": "*"。然后在项目目录下运行 npm install 。

  然后在app.js 里面引用 express-partials，引用方法：

   1.添加引用 var partials = require('express-partials');

   2.在 app.set('view engine', 'ejs'); 下面添加 app.use(partials());

 

   在需要引用模板的地方调用 layout:'模版名称' 示例

 

app.get('/reg', function (req, res) {
  res.render('reg', {
    title: '用户注册',
    layout: 'template'
  });    
});
