## 使用 jdbc 访问数据库的几个步骤
- 加载 JDBC 驱动器
- 加载 JDBC 驱动，并将其注册到DriverManager中。
- 建立数据库连接，取得 Connection 对象，一般通过 Drivermanager.getConnection(url,user,password) 方法实现
- 建立 Statement 或 PreparedStatement 对象
- 执行 SQL 语句
- 访问结果集 ResultSet 对象
- 依次关闭对象，释放资源

## Statement,PreparedStatement,CallableStatement
- Statement 用于执行不带参数的简单 SQL 语句，每次执行都需要编译该 SQL 语句
- PreparedStatement 用于执行带参数预编译的 SQL 语句
- CallableStatement 为所有 DBMS 提供一种以标准形式调用已存储过程的方法
#### PreparedStatement 的好处
- 效率更高
- 代码可读性好，可维护性好
- 安全性好，能够避免 SQL 注入