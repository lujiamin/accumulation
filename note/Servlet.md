## 什么是 Servlet
- Servlet 是采用java语言编写的服务器端程序。 主要功能是提供请求/响应的web服务模式
## 生命周期
- init() ,完成初始化工作，且只会被调用一次
- service()，每当有新的客户请求到来时，容器都会创建一个新的线程来处理该请求，接着调用service(),会根据请求的属性调用doGet()或doPost()来完成具体的响应
- destroy()，一旦执行，容器就不会再向这个Servlet发送任何请求消息了。只会被调用一次
## Servlet 三种实现方式
- 三者实现完成后都需要在 web.xml 文件中进行注册
- 继承 HttpServlet，实现 doGet() 和 doPost() 方法
```
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		response.getWriter().append("Served at: ").append(request.getContextPath());
	}
	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		doGet(request, response);
	}
```
- 实现 Servlet 接口 ，同时实现5个方法
```
	@Override
	public void destroy() {
	}

	@Override
	public ServletConfig getServletConfig() {
		return null;
	}

	@Override
	public String getServletInfo() {
		return null;
	}

	@Override
	public void init(ServletConfig arg0) throws ServletException {
	}

	@Override
	public void service(ServletRequest arg0, ServletResponse arg1) throws ServletException, IOException {
	}
```
- 继承 GenericServlet ，实现 service() 方法
```
	@Override
	public void service(ServletRequest arg0, ServletResponse arg1) throws ServletException, IOException {

	}
```