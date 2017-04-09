## IO流
- 流的本质是数据的传输，根据处理数据类型不同，可以分为字节流和字符流
- 字节流包含  InputStream 和 OutputStream (8 bit) 不支持缓存 基本单位是字节
- 字符流包含 Reader 和 Writer (16 bit) 用到了缓存 基本单元是 Unicode 码元，通常处理文本数据

## NIO(Nonblocking IO)
- 通过 Selector, Channel, Buffer来实现非阻塞的 IO 操作
- 数据可以从 Channel 读到 Buffer 中，也可以从 Buffer 写到 Channel 中
- Selector 实现了一个线程管理多个通道。创建 Selector，向其注册 Channel 
- 在处理大量并发请求时，使用 NIO 比使用 Socket 效率高很多
