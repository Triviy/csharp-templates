# Demo points

## What will be in demo?
- "dotnet new" templates. What are they and how they work?
- Who are using them now?
- How to build basic template and view it's dependencies
- What are main features?

## What is out of scope?
- CN related implementation
- Package dependencies related CN
- Folder structure

It's just a demo of base functionality that will evolve to final version of CN templates.

## dotnet new
- What is "dotnet new"? 
  https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-new
- Create basic sln, classlib, webapi
dotnet new sln -n HelloWorld
dotnet new webapi -n HelloWorld.API
dotnet new classlib -n HelloWorld.Helpers
dotnet sln add HelloWorld.API
dotnet sln add HelloWorld.Helpers

## What are dotnet templates?
https://docs.microsoft.com/en-us/dotnet/core/tools/custom-templates

You can create custom Projects, Solutions, command CLI tools
https://github.com/dotnet/aspnetcore/tree/v5.0.0/src/ProjectTemplates
https://github.com/dotnet/aspnetcore/tree/main/src/ProjectTemplates/Web.ProjectTemplates

Latest core templates are supporting "dotnet new"

## How it will work from VS 2022?

## Highlevel overview on creation process

1) Create templates
2) Pack and push code to NuGet
3) Install latest version of a template from NuGet repository
4) Create solution from a template

## How to create template?
1) Create folder structure [src]/[Content]. This is default one.
2) Add folders with solutions to [src]/[Content]. Each folder can be a separate template.
3) Create codebases
4) Add [.template.config] folder to each.
5) Create [.template.config]/[template.json]
6) Create [.template.config]/[ide.host.json]
7) Create [.template.config]/[dotnetcli.host.json]
8) Add parameters if needed
9) Add parameters conditions for solutions
10) Create nuspec file in [src] folder

11) Build nuget and push it to feed
nuget.exe pack [pathtonuspec] -OutputDirectory [outputpath]

12) Install package
dotnet new --install <PATH/PACKAGE_ID>
dotnet new --uninstall <PATH/PACKAGE_ID>

## How to use a template?
### Via dotnet CLI

#### Install SystemAPI
dotnet new cnsystemapi --db SQLServer -o ../CN/CN.SystemAPI.Orders -n Orders
dotnet new cnsystemapi --db MongoDB -o ../CN/CN.SystemAPI.Products -n Products

#### Install ProcessAPI
dotnet new cnprocessapi -o ../CN/CN.ProcessAPI.Checkout -n Checkout

#### Install PresentationAPI
dotnet new cnpresentationapi -o ../CN/CN.PresentationAPI.Search -n Search

### Via Visual Studio 2022

### Via Visual Studio for Mac

## VSIX
Can be packed to VSIX

## Materials
Create .NET Core Projects with the Command Line (https://www.youtube.com/watch?v=rZFIbbxsGmc&t=0s published 12/10)
Use an Existing .NET Core Project Template (https://youtu.be/XRrBFXN02w8 published 12/10)
Create a .NET Core Project Template (https://youtu.be/GDNcxU0_OuE published 12/10)
Create a .NET Core Project Template for Visual Studio (https://youtu.be/2hpNFrY_faI published 12/18)
Add a Parameter to a .NET Core Project Template ( https://youtu.be/o4lE_wcdmFo published 12/18)
Troubleshooting .NET Core Project Templates (https://youtu.be/Sbk87OO73jQ published 12/18)

Sample templates repo https://github.com/sayedihashimi/template-sample