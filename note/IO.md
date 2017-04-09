## IO流
- 流的本质是数据的传输，根据处理数据类型不同，可以分为字节流和字符流
- 字节流包含  InputStream 和 OutputStream (8 bit) 不支持缓存 基本单位是字节
- 字符流包含 Reader 和 Writer (16 bit) 用到了缓存 基本单元是 Unicode 码元，通常处理文本数据