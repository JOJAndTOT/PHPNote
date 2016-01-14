#Web页面跨域
>document.domain用来得到当前网页的域名，同时我们也可以给document.domain属性赋值，不过是有限制的，你只能赋成当前的域名或者基础域名。
##利用document.domain实现跨域
###前提条件
* 两个域名必须属于同一个基础域名
* 两个域名所用协议和端口都要一直。
>aaa.com的一个网页(a.html)里面 利用iframe引入了一个bbb.com里的一个网页这时在a.html里面可以看到b.html里面的内容,但是却不能利用javascript来操作它。因为这两个页面属于不同的域，在操作之前,js会检测两个页面的域是否相等，如果相等，就允许其他操作，如果不相等，就会拒绝操作。
>另一种情况，两个子域名
* aaa.xxx.com
* bbb.xxx.com
aaa 里的一个网页(a.html)引入了bbb里的一个网页(b.html)，这时a.html里同样是不能操作b.html里面的内容。这时可以通过document.domain = “xxx.com”将两个页面的domain改成一样的,此时两个页面就可以互相操作了。


#contentWindow和contentDocument
>* contentWindow 兼容各个浏览器,可取得子窗口的window对象。
>* contentDocument firefox支持，>ie8支持.可取得子窗口的document对象  
>基本用法:
>1、document.getElementById(“myiframe”).contentWindow得到对象后，就可以通过contentWindowi得到iframe包含页面的window对象,然后就可以正常访问页面元素了
>2、 可以通过contentWindow.document 得到子窗口的doucument对象
>3、$("#myiframe")[0].contentWindow.username="zhangsan"; 可以通过这种方式向iframe页面传递参数，在iframe页面window.username就可以获取到值，username是自定义的全局变量；
>4、在iframe页面通过parent可以获得主页面的window,接着就可以正常访问父亲页面的元素了


网上还有各种大神的各种牛掰解决方法，留个[连接](http://www.cnblogs.com/rainman/archive/2011/02/20/1959325.html)再说

 