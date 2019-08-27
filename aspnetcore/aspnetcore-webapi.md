# webapi

## ControllerBase 类

webapi 中的控制类都是从 ControllerBase 派生出来的，不要从 Controller 派生，因为 Controller 添加了对 View 视图的支持，aspnetcore mvc 需要处理 web 页面才使用 Controller 类派生控制类。

## ApiController 属性

- 强制使用属性路由
- 模型验证错误自动触发 HTTP 400 响应，所以无需如下代码

    ```c#
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }
    ```

    该特征也可灵活配置

- 绑定源参数推理



