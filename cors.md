浏览器的同源策略(same-origin policy)：安全因素；假如你在A网站，用一段js脚本就能访问B网站，B网站凭什么让你访问，为什么浏览器能让你随便访问别的网站呢，说不定B网站存在着各种危险，比如盗取你的密码，跨域攻击(CSRF)等。

CORS(Cross-Origin Resource Sharing),跨域资源共享，浏览器标准。

```
location / {
  add_header 'Access-Control-Allow-Origin' '*';
}
```

<https://www.ruanyifeng.com/blog/2016/04/cors.html>

<https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS>

简单请求

1、GET、POST、HEAD

2、Content-Type只能是application/x-www-form-urlencoded、multipart/form-data、text/plain

3、只有内置的、无自定义请求头

对于简单请求，浏览器自动添加Origin请求头表示来源，服务器拿到这个头用来判断是否同意这次请求（不同意时返回正常的HTTP回应，但响应头没有Access-Control-Allow-Origin头，浏览器抛出错误；同意时服务器响应包含Access-Control-Allow-Origin(必须)、Access-Control-Allow-Credentials、Access-Control-Expose-Headers头）

非简单请求

在正式请求之前，增加一次HTTP OPTIONS请求，即预检(preflight)请求。

浏览器自动添加Origin、Access-Control-Request-Method、Access-Control-Request-Headers请求头；响应头增加Access-Control-Allow-Origin、Access-Control-Allow-Credentials、Access-Control-Allow-Methods、Access-Control-Allow-Headers、Access-Control-Max-Age。

Access-Control-Max-Age设置缓存，缓存还生效时，是否发送OPTIONS预检请求只和URL有关（包括查询参数）。