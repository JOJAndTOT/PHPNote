#变量的范围
>变量的范围及它定义的上下文背景（也就是它生效的范围）。大部分的php变量只有一个单独的范围。这个单独的范围跨度同样包含了include 和require引入的文件。

```
  
<?php
$a = 1; /* global scope */ 

function Test()  
{  
    echo $a; /* reference to local scope variable */  
}

Test();  
?>  
```
>这个脚本不会有任何输出，因为，echo 语句应引用了一个局部版本的变量$a,而且在这个范围内，他并没有赋值。如果需要使用外部变量可以使用**global**关键字
```  

<?php  
$a = 1;      
$b = 2;  

function Sum()
{  
    global $a, $b;  

    $b = $a + $b;
}

Sum();  
echo $b;  
?>  
```
>以上脚本的输出将是3

#超全局变量
>$_POST、$_GET等都是可以再脚本的任何位置访问的全局变量  

**常用超全局变量**  
* $GLOBALS 一个包含了`全部变量`的全局组合数组。变量的名字就是数组的键
* $_SERVER 一个包含诸如头信息(header)、路径(path)、以及脚本位置(script locations)等等信息的数组。这个数组中的项目由Web服务器创建。OB
* $_GET
* $_POST
* $_FILES 通过http post 方式上传到当前脚本的项目数组，http文件上传变量
* $_COOKIE
* $_SESSION
* $_REQUEST 默认情况下包含了$_GET、$_POST和$_COOKIE的数组
* $_ENV 通过环境方式传递给当前脚本的变量的数组。这些变量被从PHP解析器的运行环境导入到PHP的全局命名空间。很多是由支持PHP运行的Shell提过的，并且不同的系统很可能运行着不同种类的Shell，所以不可能有一份确定的列表。

#常量 const
>在类里面定义常量用 const 关键字，而不是通常的 define() 函数。
#define函数
>* 作用域不影响对常量的访问
>* 常量值只能是字符串或数字
