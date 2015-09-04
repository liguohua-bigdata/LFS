# LFS
File System

######
    最新版貌似更快了……为虾米呢？最新数据是 24秒，快了 4秒（加了并发"行级锁"之后，怎么可能会更快？一定有其他地方的优化，一定……）
    和 C 直接读写文件速度几乎一样，意味着几乎没有额外 CPU 消耗，还用过多的解释吗？

非常非常快的文件系统，可以同时存储海量大文件和小文件，高并发<br>
存储视频音乐和图片等非常棒<br>
并且可以作为列存储<br>


链接：[github](https://github.com/ikCourage/LFS)  [git@osc](https://git.oschina.net/ikCourage/LFS_FREE)<br>

脚本语言使用 lua，why?因为快且小，而且非常简单<br>

#####设置端口号
LFS --port 9002<br>

#####设置文件存储目录
LFS --dir Storage<br>

#####打开打印模式
LFS --print<br>

#####守护进程
LFS --daemon<br>

#####设置 Socket 的收发缓存大小
LFS --inBufferSize 102400 --outBufferSize 102400<br>


测试数据
-

系统：OS X Yosemite<br>
处理器：2 GHz Intel Core i7<br>
内存：4 GB 1333 MHz DDR3<br>
硬盘：Hitachi 500 GB SATA 磁盘<br>

写入 27.5 万个分词，并构建索引（写入前先查询索引，去重）：<br>
* `全部用时：28.246 s（含本机通信用时）`
* `服务用时：28.228273082 s`

根据索引读取：<br>
* `全部用时：2 ms（含本机通信用时）`
* `服务用时：0.328847 ms`

遍历查询（第 275542 项，共 275714 项）<br>
* `全部用时：2072 ms`
* `服务用时：2071.948199 ms`


