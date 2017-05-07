## Redis
### Redis是一个开源的，高性能的 key-value 数据库
### 优势
- 性能高，读写速度快
- 丰富的数据类型: Strings, Lists, Hashes, Sets, Ordered Sets
- 所有操作都是原子性的
- 丰富的特性，支持 publish / subscribe, 通知，key过期等特性
### 特点
- Redis 的数据类型都是基于基本数据结构
- Redis 运行在内存中，但是可以持久化到磁盘
### Redis 键相关的命令
- ```del mykey```  删除键
- ```exists mykey``` 检测键是否存在
- ```expire mykey 60 ``` 设置 mykey 的过期时间为60秒
- ```keys * ``` 找出所有键名
- ```persist mykey``` 移除 mykey 过期时间，mykey 将持久化
- ```pttl mykey``` 返回 mykey 的剩余过期时间(毫秒为单位)
- ```rename mykey newkey``` 更改键名
- ```type mykey``` 返回 mykey 所存储值的类型
### String
- ```set mykey value```
- ```get mykey```