## 镜像


[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/wanni7822/hm)


### 端口

`端口` 为 `443` 。

### secret

`secret` 默认为 `a0cbcef5a486d9636472ac27f8e11a9d` 可自行设置。

## 流量中转

可以使用cloudflare的workers来`中转流量`，配置为：  

addEventListener(  
    "fetch",event => {  
        let url=new URL(event.request.url);  
        url.hostname="xx.xxxx.xx";//你的heroku域名    
        let request=new Request(url,event.request);  
        event. respondWith(  
            fetch(request)  
        )  
    }  
)  
