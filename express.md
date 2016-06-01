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
