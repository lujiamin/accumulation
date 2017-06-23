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
- ```getrange mykey m n``` 返回 mykey 中 m ~ n 子串
- ```strlen mykey``` 返回字符串长度
- ```append mykey value``` 将 value 追加到 mykey 值的尾部
### Hash
- ```hmset mykey field1 value1 [field2 value2]``` 将多个 field-value 设置到 hash 表中
- ```hmget mykey field1 [field2]``` 返回 field 对应的 value
- ```hset mykey field value``` 将 hash 表中 field 的设置为 value
- ```hget mykey field``` 返回 filed 对应的 value
- ```hgetall mykey``` 返回所有 field 和 value
- ```hkeys mykey``` 返回所有 field
- ```hvals mykey``` 返回所有 value
- ```hlen mykey``` 返回字段的数量
- ```hdel mykey filed1 [field2]``` 删除filed
- ```hexists mykey field``` 检查 field 是否存在
### List
- ```lpush mykey value1``` 向 mykey 列表头部插入元素
- ```llen mykey``` 返回列表长度
- ```lindex mykey index``` 获取索引为 index 的元素
### Set
- ```sadd mykey value1``` 向集合 mykey 中插元素value1
- ```smembers mykey``` 返回集合中所有元素
- ```sinter mykey1 mykey2``` 返回集合1和集合2的交集
- ```sunion mykey1 mykey2``` 返回集合1和集合2的并集
- ```sdiff mykey1 mykey2``` 返回集合1和集合2的差集
### Sorted Set
- ```zadd mykey score1 mem1 [score2 mem2]```向有序集合中添加一个或多个成员
- ```zcard mykey``` 返回有序集合中成员数
- ```zscore mykey mem1``` 返回 mem1 成员的分数
- ```zrank mykey mem1``` 返回有序集合中指定成员的索引
### 高级教程
- 数据备份与恢复
- 安全
- 客户端连接
- 管道技术
- 分区
