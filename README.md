## 一键部署 Gost(ss+mws) 到 heroku  [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://github.com/abdgbbgd/gost-ynk/edit/master/README.md)

> 1. 服务端部署后，view查看，显示`404 page not found`，表示部署成功。

> 2. 客户端本地代理，直接运行以下命令，本地开放端口1080，默认支持socks协议。
> ```
>    gost.exe -L=:1080 -F=ss+mwss://method:password@appname.herokuapp.com:443
> ```

> 3. 客户端[下载](https://github.com/ginuerzh/gost/releases/tag/v2.11.0)
 
> 4.  技术文档[站点](https://docs.ginuerzh.xyz/gost/)

> 5. 可通过cloudflare worker中转流量：

```js
addEventListener(
    "fetch",event => {
    let url=new URL(event.request.url);
    url.hostname="xxx.herokuapp.com";
    let request=new Request(url,event.request);
    event. respondWith(
      fetch(request)
    )
  }
)
```


### 参考 
*https://github.com/ginuerzh/gost*

*https://github.com/gfwlist/gfwlist*

*https://github.com/xausky/ShadowsocksGostPlugin*
