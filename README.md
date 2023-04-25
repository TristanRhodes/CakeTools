# CakeTools
Cake tools for build, unit test, acceptance test, load test, benchmark, and various pack/push operations.

## Overview
This build.cake file uses a `.cakemix` configuration file to determine what to pack, test, benchmark etc. It will create an initial version when first run in a project that will make a best guess default setup.

## Cakemix schema

```
public class BuildManifest
{
	public string[] NugetPackages { get; set; }
	public string[] DockerPackages { get; set; }
	public string[] DockerComposeFiles { get; set; }
	public string[] AcceptanceTests { get; set; }
	public string[] UnitTests { get; set; }
	public string[] Benchmarks { get; set; }
}
```

## Targets
* `BuildAndTest` - Build and UnitTest the projects. Writes results to `artifacts` folder.
* `BuildAndAcceptanceTest` - Spin up apps and containers. Run Specflow AT project. Writes results to `artifacts` folder.
* `BuildAndBenchmark` - Build and Benchmark the projects. Writes results to `artifacts` folder.
* `ExportApiSpecs` - Generate Swagger specs and Postman collections. Writes results to `artifacts` folder.
* `NugetPackAndPush` - Package and Push nuget packages. Writes results to `artifacts` folder.
* `DockerPackAndPush` - Package and push apps as docker images.
* `FullPackAndPush` - Package and Push nuget and docker images.

## Targets (TODO)
* `LoadTest` - Spin up apps and containers. Run K6 load tests.

## Tools
* Cake Build - https://cakebuild.net/
* GitVersion - https://gitversion.net/
* Dotnet Pack - https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-pack
