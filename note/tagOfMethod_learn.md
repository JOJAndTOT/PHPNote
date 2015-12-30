#@method
>是一个在类中使用的神奇方法，在这里你可以利用这个tag申明一个方法，但是在类里面却不能发现这个方法，但是你却能使用这个方法。但是这不是毫无条件的，你需要在类中实现__call这个方法

```  
/**  
 * @method int get($val);  
 */
class Magician{  
	function __call($method,$params){  
		if($method == 'get'){  
			return $params[0];  
		}  
	}
	
}

$magcian = new Magician();  
echo $magcian->get(5)."\n";  
```   

	输出结果是:5

    