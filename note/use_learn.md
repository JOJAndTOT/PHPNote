#USE关键字

##use作用
`use关键字3个作用`  
>  为一个类取别名  
  为一个接口取别名  
  为一个命名空间取别名  
##php use phpnamespace到底是怎么回事
>```namespace Zend\Http\PhpEnvironment;```  
>这句代码定义了一个命名空间，你可以理解为定义了一个名称为`namespace Zend\Http\PhpEnvironment`的域名，在定义了之后，下面所申明的class，interface，const等都是在申明的这个"域"里面的。当引用一个申明了命名空间的包含文件，想要调用这个里面的东西，那就必须：调整当前脚本也到这个域名例，否则就得用namespace的全称。  
比如，inc.php 文件：
namespace Zend\Http\PhpEnvironment;  
class Bar {}//定义了一个类  
则其他文件调用时：  
// 访问Foo的第一种方法，用全称  
```require 'inc.php';  
$foo = new \Zend\Http\PhpEnvironment\Bar();```  
第二种方式  
用uses后，写法如下：  
```use \Zend\Http\PhpEnvironment as pe; //定义别名   
$foo = new \pe\Bar(); //用短的别名来代替原来的```  
