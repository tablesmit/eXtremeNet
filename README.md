# eXtremeNet

[![AppVeyor branch](https://img.shields.io/appveyor/ci/gruntjs/grunt/master.svg?maxAge=2592000)](https://ci.appveyor.com/project/extremecodetv/extremenet)
[![NuGet version](https://badge.fury.io/nu/eXtremeNet.svg)](https://badge.fury.io/nu/eXtremeNet)

**eXtremeNet** - http class library for C# which includes:
 * Classes for work with proxy servers: HTTP, Socks4(a), Socks5, Chain.
 * Classes for work with HTTP 1.0/1.1 protocol: keep-alive, gzip, deflate, chunked, SSL, proxies and more.

**eXtremeNet** its a fork of [xNet](https://github.com/X-rus/xNet)


# Installation
 
Install via NuGet
 
```
PM > Install-Package eXtremeNet
```
 
# Example
 
```csharp 
using (var request = new HttpRequest("http://site.com/"))
{
    request.UserAgent = Http.ChromeUserAgent();
    request.Proxy = Socks5ProxyClient.Parse("127.0.0.1:1080");

    request
        // Parameters URL-address.
        .AddUrlParam("data1", "value1")
        .AddUrlParam("data2", "value2")

        // Parameters 'x-www-form-urlencoded'.
        .AddParam("data1", "value1")
        .AddParam("data2", "value2")
        .AddParam("data2", "value2")

        // Multipart data.
        .AddField("data1", "value1")
        .AddFile("game_code", @"C:\orion.zip")

        // HTTP-header.
        .AddHeader("X-Apocalypse", "21.12.12");
        
    // These parameters are sent in this request.
    request.Post("/").None();

    // But in this request they will be gone.
    request.Post("/").None();
}
```

#Authors

**ExtremeCodeTV:** Nikolay Desyatkov, Artem Dontsov

![VK](https://vk.com/images/faviconnew.ico?3) [VK](https://vk.com/extremecodetv)

![YouTube](https://s.ytimg.com/yts/img/favicon-vflz7uhzw.ico) [YouTube](https://www.youtube.com/channel/UCBNlINWfd08qgDkUTaUY4_w)
