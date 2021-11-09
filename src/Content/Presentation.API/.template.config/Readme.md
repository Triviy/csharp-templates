# Demo points
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

## How to create template?
1) Create folder structure [src]/[Content]. This is default one.
2) Add folders with solutions to [src]/[Content]. Each folder can be a separate template.
3) Create codebases
4) Add [.template.config] folder to each.
5) Create [.template.config]/[template.json]
6) Create [.template.config]/[ide.host.json]
7) Create [.template.config]/[dotnetcli.host.json]


## How it will work from VS 2022?


## How to create a template


## Install SystemAPI
dotnet new cnsystemapi --db SQLServer -o ../CN/CN.SystemAPI.Orders -n Orders
dotnet new cnsystemapi --db MongoDB -o ../CN/CN.SystemAPI.Products -n Products

## Install ProcessAPI
dotnet new cnprocessapi -o ../CN/CN.ProcessAPI.Checkout -n Checkout

## Install PresentationAPI
dotnet new cnpresentationapi -o ../CN/CN.PresentationAPI.Search -n Search

## VSIX
TODO