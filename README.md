# CakeTools
Cake tools for build, unit test, acceptance test, load test, benchmark, and various pack/push operations.

## Overview
This build.cake file uses a `.cakemix` configuration file to determine what to pack, test, benchmark etc. It will create an initial version when first run in a project that will make a best guess default setup.

## Cakemix C# Class

```
public class BuildManifest
{
	public string[] NugetPackages { get; set; }
	public string[] DockerPackages { get; set; }
	public string[] DockerComposeFiles { get; set; }
	public string[] Tests { get; set; }
	public string[] Benchmarks { get; set; }
	public Dictionary<string, string> ApiSpecs { get; set; }
}
```

## Cakemix Sample Schema

```
{
  "NugetPackages": [
    "./src/Template.DbApi.Model/Template.DbApi.Model.csproj",
  ],
  "DockerPackages": [
    "./src/Template.DbApi.Api/Dockerfile",
    "./src/Template.DbApi.DbUp/Dockerfile"
  ],
  "DockerComposeFiles": [
    "./docker-compose.yml",
    "./docker-compose.infra.yml",
    "./docker-compose.override.yml"
  ],
  "Tests": [
    "./test/Template.DbApi.UnitTests/Template.DbApi.UnitTests.csproj"
  ],
  "Benchmarks": [
    "./test/Template.DbApi.Benchmark/Template.DbApi.Benchmark.csproj"
  ],
  "ApiSpecs": {
    "Template.DbApi.Api": "http://localhost:5080"
  }
}
```

## Note
Use `/` for folder seperators as this works on both Windows and Linux.

## Targets
* `BuildAndTest` - Build and UnitTest the projects. Writes results to `artifacts` folder.
* `BuildAndAcceptanceTest` - Spin up apps and containers. Run Specflow AT project. Writes results to `artifacts` folder.
* `BuildAndBenchmark` - Build and Benchmark the projects. Writes results to `artifacts` folder.
* `NugetPackAndPush` - Package and Push nuget packages. Writes results to `artifacts` folder.
* `DockerPackAndPush` - Package and push apps as docker images.
* `FullPackAndPush` - Package and Push nuget and docker images.

## Targets (TODO)
* `LoadTest` - Spin up apps and containers. Run K6 load tests.

## Tools
* Cake Build - https://cakebuild.net/
* GitVersion - https://gitversion.net/
* Dotnet Pack - https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-pack
