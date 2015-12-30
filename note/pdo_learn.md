#PHP数据对象（PDO）
> 扩展为PHP访问数据库定义了一个轻量级的一致接口。

#PDO类
```bool PDO::beginTransaction ( void )```
>启动一个事物，关闭自动提交模式。自动提交模式被关闭的同时，通过PDO对象实例对数据库做出的更改直到调用PDO::commit()结束事务才被提交。调用PDO::rollBack将回滚对数据库做出的更改并将数据库连接返回到自动提交模式。

```int PDO::exec ( string $statement )```
>PDO::exec()在一个单独的函数调用中执行一条SQL语句，返回受此影响的行数。
>PDO::exec()不会从一条select语句中返回结果。对于在程序中只需要发出一次的select语句，可以考虑使用PDO::query()。对于需要发出多次的语句，可以用PDO::prepare()来准备一个PDOStatement对象并用PDOStatement::execute（）发出语句。

#PDOStatement类
>代表一条预处理语句，并在该语句被执行后代表一个相关的结果集。

```bool PDOStatement::bindColumn ( mixed $column , mixed &$param [, int $type [, int $maxlen [, mixed $driverdata ]]] )```

>安排一个特定的变量绑定到一个查询结果集中给定的列。每次调用PDOStatement::fetch()或PDOStatement::feechAll()都将更新所有绑定到列的变量。

```bool PDOStatement::execute ([ array $input_parameters ] )```
>执行预处理过得语句。如果预处理过的语句含有参数标记，必须选择下面其中一种做法：  
*   调用PDOStatement::bindParam()绑定PHP变量到参数标记：如果没有的哈，通过关联参数标记绑定的变量来传递输入值和取得输出值
*   或传递一个只作为输入参数值的数组

###事务与自动提交
>事务支持四大特性（ACID）原子性、一致性、隔离性和持久性。事务通常是通过吧一批更改“积蓄”起来然手使之同时生效而实现的；不是每一种数据库都支持事务，一次当第一次打开连接是，PDO需要在所谓的“自动提交”模式下运行。自动提交模式意味着，如果数据库支持，运行的每一个查询都有它自己的隐式事务，如果数据不支持事务，则没有。如果需要一个事务，则必须用PDO::beginTransaction();  
>[参考链接](http://php.net/manual/zh/pdo.transactions.php)




