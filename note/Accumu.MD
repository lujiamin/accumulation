### 下面哪个不是标准的 Statement 类？
- Statement 最基本的用法，采用字符串拼接的方式
- PreparedStatement 对 Statement 中的 SQL 语句进行预编译，同时检查合法性，效率高
- CallableStatement 接口扩展 PreparedStatement，用来调用存储过程,它提供了对输出和输入/输出参数的支持
- BatchedStatement  不是