# Blazor Introduction

## Project Structure

```
blazor-project/
├─ Components/
│  ├─ Layout/
│  ├─ Pages/
│  ├─ _Imports.razor
│  ├─ App.razor
│  ├─ Routes.razor
├─ obj/
├─ Properties/
├─ wwwroot/
│  ├─ lib/
│  ├─ app.css
│  ├─ favicon.png
├─ appsettings.Development.json
├─ appsettings.json
├─ Blazor-Project.csproj
├─ Blazor-Project.sln
├─ Program.cs
```

### Blazor-Project.csproj

Written in XML format, defines the configuration, dependencies, and build settings for the Blazor Application

### Program.cs

The entry point of the Application. Sets up the app's environment, services, and configuration.<br>
`var builder = WebApplication.CreateBuilder(args)` creates a new instance of the web application builder by invoking thhe static CreateBuilder Method<br>
`builder.Services....`
We then configure the services for the application, such as Blazor components and Interactive Server Components in this project<br>
`var app = builder.Build();`
This line then builds our application instance
Below this we add the middleware for the application<br>
`app.UseHttpsRedirection();`
Redirects HTTP request to HTTPS<br>
`app.UseStaticFiles();`
Serves static files such as HTML, CSS, JavaScript from the wwwroot directory<br>
`app.UseAntiforgery();`
Protects against cross-site requests forgery<br>
`app.MapRazorComponents<App>().AddInteractiveServerRenderMode();`
Maps the App component as the root component for the Razor Components, enabling interactive server rendering mode<br>
`app.Run();`
Runs the application, making it ready to listen for, and handle HTTP requests

### wwwroot

Contains static web assests which are served directly to the client's web browser (HTML, CSS, JS, Images, and other static files)

### Properties

Contains the `launchSettings.json` file which contains information regarding how the application is launched during development

### appsettings.json

Contains configuration settings for the application needed during run time, such as connections strings, logging levels, default values for parameters, third party service configurations, etc...

### appsettings.Development.json

Stores configuration settings specifically for the development environment

### Components

We can find all of the components for the app here.<br>
`App.razor` is our root component where the root HTML document is located as well as the Blazor Router and the Blazor script tags <br>
`Routes.razor` is where the routing configuration for the app is defined, it specifies the mapping between URLs and their corresponding components or pages to render
