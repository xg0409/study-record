<h1>this</h1>
<p>javascript里的this指针逻辑上的概念也是实例化对象，这一点和java语言里的this指针是一致的，但是javascript里的this指针却比java里的this难以理解的多，究其根本原因我个人觉得有三个原因：</p>
<pre>
原因一：javascript是一个函数编程语言，怪就怪在它也有this指针，说明这个函数编程语言也是面向对象的语言，
        说的具体点，javascript里的函数是一个高阶函数，编程语言里的高阶函数是可以作为对象传递的，
        同时javascript里的函数还有可以作为构造函数，这个构造函数可以创建实例化对象，结果导致方法
        执行时候this指针的指向会不断发生变化，很难控制。

原因二：javascript里的全局作用域对this指针有很大的影响，由上面java的例子我们看到，this指针只有在使用
    <br/>new操作符后才会生效，但是javascript里的this在没有进行new操作也会生效，这时候this往往会指向全局对象window。

原因三：javascript里call和apply操作符可以随意改变this指向，这看起来很灵活，但是这种不合常理的做法破
        <br/>坏了我们理解this指针的本意，同时也让写代码时候很难理解this的真正指向
</pre>
