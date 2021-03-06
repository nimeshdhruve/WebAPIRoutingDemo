# WebAPIRoutingDemo
After upgrading to Asp.Net Core 2.2 (from Asp.Net Core 2.1), Url.RouteURL seems to be broken.

This repo has code to demonstrate the issue. 

In file [Startup.cs](https://github.com/nimeshdhruve/WebAPIRoutingDemo/blob/master/WebApiDemo/Startup.cs) if you uncomment [line ](https://github.com/nimeshdhruve/WebAPIRoutingDemo/blob/master/WebApiDemo/Startup.cs#L30) `setupAction.EnableEndpointRouting = false` the URL will get correctly generated other wise URL won't generate. 

However by setting `EnableEndpointRouting` to `false` we loose the new Routing features introduced with 2.2.

The code for generating URL uses Url.RouteUrl:
```
Example: 
Url.RouteUrl("ControllerOnlyRouteName", new { controller= "MyApi"})
```
## Example
![Output](Example.jpg)


Referred in:
 - https://github.com/aspnet/AspNetCore/issues/4556
 - https://github.com/aspnet/Docs/issues/9886
