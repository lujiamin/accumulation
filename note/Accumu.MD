### 下面哪个不是标准的 Statement 类？
- Statement 最基本的用法，采用字符串拼接的方式
- PreparedStatement 对 Statement 中的 SQL 语句进行预编译，同时检查合法性，效率高
- CallableStatement 接口扩展 PreparedStatement，用来调用存储过程,它提供了对输出和输入/输出参数的支持
- BatchedStatement  不是

### final,finally,finalize
- final 用来修饰属性、方法和类。分别表示属性不可变、方法不可覆盖、类不可继承
- finally 作为异常处理的一部分，只能用在 try,catch 语句中。finally 语句块中代码一定会被执行，通常用来释放资源
- finalize 是 Object 类的一个方法，在垃圾回收器执行时会调用被回收对象的 finalize() 方法

### 关键字static
- 被 static 修饰的变量、方法可以不创建对象就能访问。
- static 成员方法不能调用非 static 方法。
- static 代码块是独立于成员变量和成员函数的代码块。JVM 在加载类是会执行 static 代码块。
- static 内部类，只能访问外部类中的静态成员和静态方法。
- 不能在成员函数内部定义 static 变量

### volatile
- 中文意思:不稳定的
- 被 volatile 修饰的变量，系统每次用到它时都是直接从对应的内存中提取，而不会利用缓存。
- volatile 不能保证操作的原子性(这种操作一旦开始就会一直运行到结束，中间不会切换到另一个线程)

### "==",equals,hashCode 区别
- "==" 用来比较两个变量的值是否相等。但是无法实现两个对象的内容是否相等
- equals 是 Object 类提供的方法，在没有被覆盖的情况下，equals 等同于 "==",比较的是引用。但是 String 的 equals 方法是用于比较两个独立对象的内容是否相同，即堆中的内容是否相同
- hashCode() 方法是从 Object 类继承而来，在没有重写的情况下，任何对象的 hashCode()方法都是不相等的。但是 String 对象的 hashCode 只跟内容有关。
