# CakeTools
Cake tools for build, unit test, acceptance test, load test, benchmark, and various pack/push operations.

## Overview
This build.cake file uses a `.cakemix` configuration file to determine what to pack, test, benchmark etc. It will create an initial version when first run in a project that will make a best guess default setup.

## Targets
* `BuildAndTest` - Build and UnitTest the projects
* `BuildAndBenchmark` - Build and UnitTest the projects
* `PackAndPush` - Package and Push nuget packages

## Targets (TODO)
* `AcceptanceTest` - Spin up apps and containers. Run Specflow AT project.
* `LoadTest` - Spin up apps and containers. Run K6 load tests.
* `DockerPackAndPush` - Package and push apps as docker images.

## Tools
* Cake Build - https://cakebuild.net/
* GitVersion - https://gitversion.net/
* Dotnet Pack - https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-pack
