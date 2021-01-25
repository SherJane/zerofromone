浏览器的同源策略(same-origin policy)：安全因素；假如你在A网站，用一段js脚本就能访问B网站，B网站凭什么让你访问，为什么浏览器能让你随便访问别的网站呢，说不定B网站存在着各种危险，比如盗取你的密码，跨域攻击(CSRF)等。

CORS(Cross-Origin Resource Sharing),跨域资源共享，浏览器标准。

```
location / {
  add_header 'Access-Control-Allow-Origin' '*';
}
```

<https://www.ruanyifeng.com/blog/2016/04/cors.html>

<https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS>