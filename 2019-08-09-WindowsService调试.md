# c# windows service 调试

vs 建的 windows service 项目不便于调试，我更情愿用 topshelf 来建服务项目，方便调试

以下这个方法调试 vs 建的 windows service 项目简单可行：

```c#
static class Program
{
    static void Main()
    {
        ServiceBase[] ServicesToRun;
        ServicesToRun = new ServiceBase[]
        {
            new MyService()
        };
        ServiceBase.Run(ServicesToRun);
    }
}
```

改成

```c#
static class Program
{
    static void Main()
    {
        #if(!DEBUG)
           ServiceBase[] ServicesToRun;
           ServicesToRun = new ServiceBase[]
            {
                new MyService()
            };
           ServiceBase.Run(ServicesToRun);
         #else
           MyService myServ = new MyService();
           myServ.Process();
           // here Process is my Service function
           // that will run when my service onstart is call
           // you need to call your own method or function name here instead of Process();
         #endif
    }
}
```

参考：

[How to Debug or Test your Windows Service Without Installing it...](https://www.codeproject.com/Tips/261190/How-to-Debug-or-Test-your-Windows-Service-Without)
