# Getting Started with Carter Framework for ASP.NET Core

## Overview

Carter is an open-source routing library for ASP.NET Core, which allows you to create simple and elegant routing mechanisms for your ASP.NET Core applications. It is especially suitable for building Microservices and APIs.

---

## Advantages of Carter Framework

Here are some of the advantages of using Carter framework for MinimalAPI:

Carter uses minimal dependency injection (DI) and HTTP abstractions, which make the setup minimalistic and easy to use.
Carter allows creating APIs and Web applications with minimal boilerplate code.
Carter provides a minimalistic and highly extensible API for building HTTP-based services using .NET.
Carter enables the developer to define APIs as a set of smaller, independent modules, each encapsulating a specific unit of functionality.
Carter's routing API is designed to be efficient, low-level, and highly testable.
Getting Started
Installing the NuGet Package

To get started with Carter, you need to install the Carter nuget package. You can do this using the Package Manager Console by running the following command:

```C#
Install-Package Carter
```

Creating a New Carter Module

To create a new Carter module, you need to define a new class that inherits from the CarterModule class. In this class, you can define your API endpoints using the available HTTP verbs such as Get, Post, Put, Delete, etc. Here is an example of a simple Carter module that defines a GET endpoint:

```c#
using Carter;
using Microsoft.AspNetCore.Http;

public class MyModule : CarterModule
{
    public MyModule()
    {
        Get("/hello", async (req, res) => 
        {
            await res.WriteAsync("Hello, World!");
        });
    }
}
```

In the above example, we created a new Carter module called MyModule and defined a single endpoint that responds to GET requests to /hello and returns the string "Hello, World!".

## Adding Carter to Your Application

To add Carter to your ASP.NET Core application, you need to add it to the service collection in the Startup class' ConfigureServices method and then add the endpoints using the MapCarter extension method in the Configure method. Here is an example of how you can set up the Carter middleware in your application:

```c#
using Carter;
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.DependencyInjection;

public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddCarter();
    }

    public void Configure(IApplicationBuilder app)
    {
        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapGet("/", async context =>
            {
                await context.Response.WriteAsync("Hello World!");
            });

            endpoints.MapCarter();
        });
    }
}
```

In the above example, we added the AddCarter method to the ConfigureServices method to register Carter with the service collection. We then added the endpoints using the MapGet method to define a default endpoint and the MapCarter method to map all the endpoints defined in the Carter modules.

Using Carter Modules in Your Application

Once you have added the Carter middleware to your application, you can start using the Carter modules you defined in your application. Here is an example of how to use the MyModule we defined earlier:

```c#
using Microsoft.AspNetCore.Builder;

public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapCarter();

            // Alternatively, you can map individual modules like this:
            // endpoints.MapCarter<MyModule>(); 
        });
    }
}
```

In the above example, we mapped all the endpoints defined in the Carter modules using the MapCarter method. Alternatively, you can map individual modules by calling the MapCarter method with the specific Carter module type. For example, if we wanted to use the MyModule module defined earlier, we could add the line

```c#
endpoints.MapCarter<MyModule>();
```

instead of :

```c#
endpoints.MapCarter();.
```

By mapping individual modules, you can have more control over which endpoints are available in your application. Additionally, you can define multiple Carter modules in your application, each containing a specific set of endpoints and functionality.
