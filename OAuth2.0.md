<https://datatracker.ietf.org/doc/rfc6749/?include_text=1>

给予第三方临时访问权限，access_token对应临时权限，过期失效；scope对应权限范围

首先第三方需要备案，获得client_id和client_secret，确定第三方身份

为什么先要有个code？授权服务器根据客户端传的redirect_url返回给客户端302重定向状态码，然后客户端再把授权码code传给客户端服务器，故如果直接返回token容易暴露。

