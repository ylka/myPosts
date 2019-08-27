# AspNetCore 创建和发布

/*2019-08-01 21:34:18*

vs 操作没什么好说的，记录命令行的操作

- 创建

>dotnet new webapp -o aspnetcoreapp

- 发布

> dotnet publish

## windows

- 安装 dotnet hosting
- 安装 iis，在 iis 站点的模块中，确保有 AspNetCoreModule 托管模块
- 设置 iis 站点应用线程池 .NET CLR version 为 No Managed Code

将发布的文件拷到站点目录。

以上，默认运行 ok。

## linux

## docker
