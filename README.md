# tdd-cicd-kata

Hi,

This repository is meant to provide a quick start around some Key Engineering topics

## Test Driven Development

Tech Stack: .Net Core C#

Pre-requirements:

.Net 6

https://dotnet.microsoft.com/en-us/download/dotnet/6.0

Visual Studio Code

https://code.visualstudio.com/download

### Create Project Skeleton

Create Solution

`dotnet new sln --name "Kata"`

Create Test Project

`dotnet new xunit --name "Tests"`

Create Production Code Project

`dotnet new web --name "API"`

Import "API Project" to tests

`cd Tests`
`dotnet add reference ../API/API.csproj`

Add `API` and `Tests` projects into the solution

`dotnet sln add Kata.sln Tests/Tests.csproj`
`dotnet sln add Kata.sln API/API.csproj`

Make the test fail to configure the pipeline in `Tests\UnitTest1.cs`

```csharp
using Xunit;

namespace Tests;

public class UnitTest1
{
    [Fact]
    public void Test1()
    {
        Assert.Equal(false, true);
    }
}
```

Install the XUnit Test Explorer

Name: .NET Core Test Explorer
Id: formulahendry.dotnet-test-explorer
Description: Test Explorer for .NET Core (MSTest, xUnit, NUnit)
Version: 0.7.8
Publisher: Jun Han
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=formulahendry.dotnet-test-explorer

Execute the tests

`dotnet test`

## Continuos Delivery

Tech Stack: Github Actions
