#PHP的自动加载

>PHP5.2版本更新了自动加载。自动加载就是我们在new一个class的时候，不需要手动去写require来导入这个class.php文件,程序自动帮助我们加载导入进来。

##__autoload的使用

 >自动加载原理，就是在我们自动加载的原理，就是在我们new一个class的时候，PHP系统如果找不到你这个类，就会去自动调用本文件中的__autoload($class_name)方法，我们new的这个class_name 就成为这个方法的参数。所以我们就可以在这个方法中根据我们需要new class_name的各种判断和划分就去require对应的路径类文件，从而实现自动加载。
 
**DB.php**  
```
class DB{                                                                              
	public function __construct(){        
		echo 'Hello';  
	}    
}
```  

**index.php**  
```
    $db = new DB();  
    function __autoload($className)  
    {
        require $className . '.php';  
    }
```
根据上面的就可以正确的输出了


##spl\_autoload\_register的使用
>小的项目，用__autoload()就能实现基本的自动加载了。但是如果一个项目过大，或者需要不同的自动加载来加载不同路径的文件，这个时候__autoload就悲剧了，原因是一个项目中仅能有一个这样的 __autoload() 函数，因为 PHP 不允许函数重名，也就是说你不能声明2个__autoload()函数文件，否则会报致命错误

`spl_autoload_register($param)`这个参数的形式
>sql_autoload_resister('load_function'); //函数名  
sql_autoload_resister(array('load_object', 'load_function')); //类和静态方法
sql_autoload_resister('load_object::load_function'); //类和方法的静态调用

>//php 5.3之后，也可以像这样支持匿名函数了。
spl_autoload_register(function($className){  
    if (is_file('./lib/' . $className . '.php')) {  
       require './lib/' . $className . '.php';  
    }  
});

简单示例

```function load1($className)  
{   
    echo 1;  
    require $className . '.php';  
}  
spl_autoload_register('load1'); //将load1函数注册到自动加载队列中。  ```
