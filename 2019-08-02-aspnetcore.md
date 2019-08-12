# AspNetCore 学习

## Program Class

### 1 CreateDefaultBuilder

创建 IWebHostBuilder 实例，默认的一些动作：

- use Kestrel as the web server
- configure it using the application's configuration providers
- configure the ILoggerFactory to log to the console and debug output
- enable IIS integration
- set the ContentRootPath to the result of GetCurrentDirectory()

## Windows 部署错误

### 1 HTTP Error 502.5

控制台命令行诊断，根据错误信息定位问题

- Open Command Prompt
- Navigate to bin directory of your project. Let's assume your project name is 'test'
- Run 'dotnet .\test.dll' and you will see something like Microsoft.Aspnetcore.all version 2.1.2 was not found.
- Then run 'dotnet -info' and you will see your .netcore runtime. Mine was 2.1.1.
So I downgraded my Microsoft.Aspnetcore.all nuget package to 2.1.1 and it worked after.

Alternatively, you could upgrade .netcore runtime but that's more work :)
The error on web browser and events log is useless. Can't wait for .netcore 3 :P

相关链接：

[HTTP Error 502.5](https://github.com/aspnet/IISIntegration/issues/945)

### 2 hostfxr.dll 找不到

>The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed.

打个 [KB2533623](https://support.microsoft.com/zh-cn/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) 补丁

相关链接：

[Prerequisites for .NET Core on Windows](https://docs.microsoft.com/en-us/dotnet/core/windows-prerequisites?tabs=netcore2x)

## 命令行发布

1 Debug
>dotnet publish -c Debug -r win10-x64

2 Release
>dotnet publish -c Release -r win10-x64
