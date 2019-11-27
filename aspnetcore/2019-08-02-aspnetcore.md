# AspNetCore 学习

## Program Class

### 1 CreateDefaultBuilder

创建 IWebHostBuilder 实例，默认的一些动作：

- use Kestrel as the web server
- configure it using the application's configuration providers
- configure the ILoggerFactory to log to the console and debug output
- enable IIS integration
- set the ContentRootPath to the result of GetCurrentDirectory()

## 命令行发布

```shell
dotnet publish -c Release -r win-x64 -o dist/win-x64
dotnet publish -c Release -r osx-x64 -o dist/osx-x64
dotnet publish -c Release -r linux-x64 -o dist/linux-x64
```

## WebApi 几点小技巧

- 路由小写
- 路由版本
- swagger 丝袜哥
- 允许跨域请求

相关链接

[或许是你应该了解的一些 ASP.NET Core Web API 使用小技巧](https://www.cnblogs.com/danvic712/p/11255423.html)
