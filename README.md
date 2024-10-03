# James 的第一支 Helloworld web api by .net 8.0
## 建立方式

在 Visual Studio 建立新專案 web api 

![image](https://github.com/jawa560/Helloworld/blob/master/images/create_1.png?raw=true)

建立好後，在Controllers 資料夾建立一個 helloworld.cs 

![image](https://github.com/jawa560/Helloworld/blob/master/images/create_2.png?raw=true)

輸入程式碼如下:
```
  using Microsoft.AspNetCore.Mvc;
  namespace Helloworld.Controllers
  {
      [Route("[controller]")]
      [ApiController]
      public class HelloWorldController : ControllerBase
      {
          // GET: api/<HelloWorldController>
          [HttpGet]
          public string Get()
          {
              return  "Hello World!";
          }
          // GET api/<HelloWorldController>/5
          [HttpGet("{id}")]
          public string Get(int id)
          {
              return "value";
          }
          // POST api/<HelloWorldController>
          [HttpPost]
          public void Post([FromBody] string value)
          {
          }
          // PUT api/<HelloWorldController>/5
          [HttpPut("{id}")]
          public void Put(int id, [FromBody] string value)
          {
          }
          // DELETE api/<HelloWorldController>/5
          [HttpDelete("{id}")]
          public void Delete(int id)
          {
          }
      }
  }
```
programs.cs 內容不用修改，應該如下:
```
var builder = WebApplication.CreateBuilder(args);

// Add services to the container.

builder.Services.AddControllers();

var app = builder.Build();

// Configure the HTTP request pipeline.

app.UseAuthorization();

app.MapControllers();

app.Run();

```
如果要指定用 port 4000，那在[專案] 上按右鍵，選[屬性]，進入屬性設定頁面後，到[偵錯]裡如下圖設定 port 及預設路徑 

![image](https://github.com/jawa560/Helloworld/blob/master/images/env_1.png?raw=true)

![image](https://github.com/jawa560/Helloworld/blob/master/images/env_2.png?raw=true)
