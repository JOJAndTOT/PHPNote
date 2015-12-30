##简介
   是 PHP 用来管理依赖（dependency）关系的工具。你可以在自己的项目中声明所依赖的外部工具库（libraries），Composer 会帮你安装这些依赖的库文件。
##安装
   安装Composer，你只需要下载composer.phar可执行文件即可

```
  curl -sS https://getcomposer.org/installer | php
```

   检查Composer是否正常工作，只需通过`php`来执行`phar`
```
  php composer.phar
```

##项目中使用`Composer

*  在项目中使用Composer需要一个`compser.json`文件。

*  之后执行下面语句进行依赖包安装  

  ```
   php composer.phar install
  ```

>**注意：**
>本机通过vagrant up安装统一的环境，其composer已经全局安装了，所以只需要执行 `composer install`即可。本次主要是安装swiftmailer的依赖包，局官网文档描述使用composer执行下述语句即可:
>```
>composer require swiftmailer/swiftmailer
>```
###最后
  * [Composer参考中文文档](http://docs.phpcomposer.com/01-basic-usage.html)