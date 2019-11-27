# 不使用 ASPNETCORE IDENTITY 的cookie认证

## 1 Configuration

In the `Startup.ConfigureServices` method, create the Authentication Middleware services with the AddAuthentication and AddCookie methods:

```c#
services.AddAuthentication(CookieAuthenticationDefaults.AuthenticationScheme)
    .AddCookie();
```
