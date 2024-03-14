# Repro of FluentNavMenu Issue

This repository reproduces the _Expanded_ issue found in **FluentNavMenu**.

Script to create projects

```powershell
md server-hosted
pushd
cd server-hosted
dotnet new fluentblazor -int None -o None
dotnet new fluentblazor -int Server -o Server
dotnet new fluentblazor -int WebAssembly -o WebAssembly
dotnet new fluentblazor -int Auto -o Auto
popd

md wasm
pushd
cd wasm
dotnet new fluentblazorwasm
popd

md maui-blazor
pushd
cd maui-blazor
dotnet new maui-blazor
popd

dotnet new solution
dotnet sln add .\server-hosted\None\
dotnet sln add .\server-hosted\Server\
dotnet sln add .\server-hosted\WebAssembly\WebAssembly\
dotnet sln add .\server-hosted\WebAssembly\WebAssembly.Client\
dotnet sln add .\server-hosted\Auto\Auto\
dotnet sln add .\server-hosted\Auto\Auto.Client\
dotnet sln add .\wasm\
dotnet sln add .\maui-blazor\
```
