# CORS

## 概述

在b站开源的代码中CORS中间件默认允许的域名为

```go
allowOriginHosts = []string{
    ".bilibili.com",
    ".biligame.com",
    ".bilibili.co",
    ".im9.com",
    ".acg.tv",
    ".hdslb.com",
}
```

默认验证方式为

``` go
AllowOriginFunc: func(origin string) bool {
    for _, host := range allowOriginHosts {
        if strings.HasSuffix(strings.ToLower(origin), host) {
        return true
        }
    }
    return false
},
```

所以子域名也是可以COR的
