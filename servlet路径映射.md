根据Servlet规范，有4种匹配方式(Mapping Requests to Servlets章12.2)：

1、精确匹配

2、路径匹配，以/开头，以/*结尾

3、后缀名匹配，以*.开头，如"*.*"可以匹配/api/demo1.*

4、缺省匹配，即固定值/。SpringMVC的DispatcherServlet的匹配路径默认就是/，会拦截各种各样的请求，再内部处理。(不拦截jsp是因为有专门的JspServlet)

