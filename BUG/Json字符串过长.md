# Json字符串过长

>BUG产生时间：
>	2023/8/25

## 主要问题：

```
Message": "使用 JSON JavaScriptSerializer 进行序列化或反序列化时出错。字符串的长度超过了为 maxJsonLength 属性设置的值。"
```
具体原因是在页面初始化时，本身是从数据库中导出按时间排序的最近的50条数据，但由于返回的数据为object格式，Json无法解析全部内容。


## 解决方案：
在进行提取数据时，减少数据的量。
example：本身是提50条数据，现改为提30条。


## 完整报错内容：

```json
{
    "config": {
        "transformRequest": {},
        "transformResponse": {},
        "timeout": 0,
        "xsrfCookieName": "XSRF-TOKEN",
        "xsrfHeaderName": "X-XSRF-TOKEN",
        "maxContentLength": -1,
        "headers": {
            "Accept": "application/json, text/plain, */*",
            "Content-Type": "application/json;charset=utf-8"
        },
        "method": "post",
        "url": "CarGoodsRegistration.aspx/SelectFifty",
        "data": "{}"
    },
    "request": {},
    "response": {
        "data": {
            "Message": "使用 JSON JavaScriptSerializer 进行序列化或反序列化时出错。字符串的长度超过了为 maxJsonLength 属性设置的值。",
            "StackTrace": "   在 System.Web.Script.Serialization.JavaScriptSerializer.Serialize(Object obj, StringBuilder output, SerializationFormat serializationFormat)\r\n   在 System.Web.Script.Serialization.JavaScriptSerializer.Serialize(Object obj, SerializationFormat serializationFormat)\r\n   在 System.Web.Script.Services.RestHandler.InvokeMethod(HttpContext context, WebServiceMethodData methodData, IDictionary`2 rawParams)\r\n   在 System.Web.Script.Services.RestHandler.ExecuteWebServiceCall(HttpContext context, WebServiceMethodData methodData)",
            "ExceptionType": "System.InvalidOperationException"
        },
        "status": 500,
        "statusText": "",
        "headers": {
            "content-length": "758",
            "content-type": "application/json; charset=utf-8",
            "date": "Fri, 25 Aug 2023 08:17:55 GMT",
            "jsonerror": "true",
            "server": "Microsoft-IIS/10.0",
            "x-powered-by": "ASP.NET",
            "x-sourcefiles": "=?UTF-8?B?RDpcQ2hlblpoYW5nXEdvb2RzLUdvb2RzXENhckdvb2RzUmVnaXN0cmF0aW9uLmFzcHhcU2VsZWN0RmlmdHk=?="
        },
        "config": {
            "transformRequest": {},
            "transformResponse": {},
            "timeout": 0,
            "xsrfCookieName": "XSRF-TOKEN",
            "xsrfHeaderName": "X-XSRF-TOKEN",
            "maxContentLength": -1,
            "headers": {
                "Accept": "application/json, text/plain, */*",
                "Content-Type": "application/json;charset=utf-8"
            },
            "method": "post",
            "url": "CarGoodsRegistration.aspx/SelectFifty",
            "data": "{}"
        },
        "request": {}
    }
}
```



