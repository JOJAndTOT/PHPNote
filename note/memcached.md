#概述
>memcached 是一个高性能分布式的内存对象缓存系统，通常用于降低数据库加载压力以提高动态web应用的响应速度。此扩展使用了libmemcached 库提供的api与memcached服务器端进行交互。他同样提供了一个session处理(memcached)。[libmemcached](http://libmemcached.org/libMemcached.html)

libMemcached is designed to provide the greatest number of options to use Memcached.
只在提供更好的选项来使用memecached(好烦，翻译不能),一些特性：
* 支持异步和同步的传输支持
* 一致性的哈希和分布
* 可调用(或者启用)哈希算法来匹配关键字
* 对访问较大对象的支持
* 本地复制(没懂)
* 完整的指导和文档
* 提供工具来管理你的memcached 网络

>memecached 会使用部分你不需要或者很少使用的内存，它会帮助你更好的利用机器的内存。
>* 每一个节点是完全独立的
>* 每个节点可以利用其它节点的内存
