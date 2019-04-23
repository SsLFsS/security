# CSRF

## 概述

b站的CSRF中间件允许使用callback和jsonp参数进行jsonp调用,鉴权方式为Referer header.
允许范围如下

``` go
_allowHosts = []string{
        ".bilibili.com",
        ".bilibili.co",
        ".biligame.com",
        ".im9.com",
        ".acg.tv",
        ".hdslb.com",
}
_allowPatterns = []string{
        // match by wechat appid
        `^http(?:s)?://([\w\d]+\.)?servicewechat.com/(wx7564fd5313d24844|wx618ca8c24bf06c33)`,
}

```