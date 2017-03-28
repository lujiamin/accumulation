- 下面哪个不是标准的 Statement 类？
 - Statement 最基本的用法，采用字符串拼接的方式
 - PreparedStatement 对 Statement 中的 SQL 语句进行预编译，同时检查合法性，效率高
 - CallableStatement 接口扩展 PreparedStatement，用来调用存储过程,它提供了对输出和输入/输出参数的支持
 - BatchedStatement  不是
***
- String,StringBuffer,StringBuilder,StringTokenizer
 - String 不可变类 , 可以使用 String s=new String("xx"); 或者 String s="xx";进行实例化
 - StringBuffer 可变类，只能使用 StringBuffer sb=new StringBuffer("xx");进行实例化。使用sb.append("yy");进行修改添加
 - StringBuilder 执行效率最高，但是不是线程安全的。多线程时，只能使用StringBuffer。
 - StringTokenizer 用来分割字符串，使用nextToken()方法实现