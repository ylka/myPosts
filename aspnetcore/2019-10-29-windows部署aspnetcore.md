# Windows 部署 aspnetcore 站点

> 一般的问题都是漏打补丁

## 1 IIS 设置

- 安装 dotnet hosting/runtime。
- 安装 iis，在 iis 站点的模块中，确保有 AspNetCoreModule 托管模块。
- 设置 iis 站点应用线程池 .NET CLR version 为 No Managed Code。

将发布的文件拷到站点目录。

以上，默认运行 ok。

## 2 HTTP Error 502.5

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

## 3 hostfxr.dll 找不到

>The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed.

打个 [KB2533623](https://support.microsoft.com/zh-cn/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) 补丁

相关链接：

[Prerequisites for .NET Core on Windows](https://docs.microsoft.com/en-us/dotnet/core/windows-prerequisites?tabs=netcore2x)
