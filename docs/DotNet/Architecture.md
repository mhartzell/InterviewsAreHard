# Architecture
.NET is a general purpose development ecosystem.  It supports multiple programming languages and target platforms for deployment.  A .NET application is developed and runs in one or more implementations of .NET.

# Common Language Infrastructure (CLI)
The Common Language Infrastructure (CLI) is an open specification developed by Microsoft and standardized by ISO and ECMA.  It describes an agnostic execution environment and a mechanism for language interoperability.  It defines four main components.

## The Common Type System (CTS)
The Common Type System (CTS) is a standard that specifies how type definitions and specific values of types are represented in computer memory.  It is intended to allow programs written in different languages to share information.
## The Metadata
Information about program structure that is language-agnostic.

## The Common Language Specification (CLS)
The Common Language Specification (CLS) is a set of base rules to which any language targeting the CLI should conform in order to interoperate with other CLS-compliant languages.

## The Virtual Execution System
The Virtual Execution System (VES) loads and executes CLI-compatible programs, using metadata to combine separately generated pieces of code at runtime.

## Supported Languages
.NET currently supports three languages:

- C#
- F#
- VB.NET

# .NET Standard
The .NET Standard is a set of APIs that are implemented by each .NET implementation.  It is a specification of APIs that make up a uniform set of contracts against which code is compiled, allowing portability between different .NET implementations.  

.NET Standard also happens to be a target framework.  Code that targets .NET Standard can run on any implementation that supports that version of the Standard.

# .NET Implementations
A .NET implementation is required to provide one or more runtimes, as well as a class library that implements the .NET Standard.  Optionally, an implementation may provide one or more application frameworks as well as development tooling.  

## .NET Core
.NET Core is a cross-platform implementation of .NET and is designed to handle server and cloud workloads at scale.  

## .NET Framework
The .NET Framework is the original .NET implementation that has existed since 2002.  .NET 4.5 and later implement the .NET Standard.  It contains additional Windows-specific APIs.

## Mono
Mono is a .NET implementation that is mainly used when a small runtime is required.  It powers Xamarin applications on mobile devices, as well as the Unity game engine.

## Universal Windows Platform
UWP is a .NET implementation that is used for building modern, touch-enabled Windows applications and software for the Internet of Things.  

# Runtime
A runtime is the execution environment for a managed program.    It is responsible for taking managed code, compiling it into machine code and then executing it.  It then provides important services such as memory management, security boundaries, type safety, etc.  

## Common Language Runtime (.NET Framework)
The CLR provides a run-time environment, which provides code functionality via compilers and tooling and executes code in a managed environment. To enable the runtime to provide services to managed code, language compilers must emit metadata that describes the types, members, and references in the code.  Code written in different languages is compatible and can be tightly integrated.

The version of the .NET Framework does not necessarily correspond to the version number of the CLR it includes.

## Core Common Language Runtime (.NET Core)

## .NET Native (UWP)

## Mono Runtime

# Libraries
.NET has an expansive set of class libraries that provide implementations for many general and app-specific types, algorithms and utility functions.

## Base Class Libraries
The BCL provides the most foundational types and utility functionality and are base of all other .NET class libraries.  They provide general purpose implementations and take a middle-ground approach to performance concerns.

## Primitive Types
Base types used across all applications.

## Data Structures
Mostly collections, but include other types such as Uri and DateTime.

## Utility APIs
HttpClient, StreamReader, etc.

# Tooling and Common Infrastructure
.NET has an extensive set of tools and infrastructure components that work with every implementation.  They include:

- The .NET languages and their compilers
- The .NET project system
- MSBuild
- NuGet
- Open-source build orchestration tools (CAKE, FAKE)

# Intermediate Language
Managed code does not compile to machine code, but rather to Intermediate Language (IL).  IL is independent from any specific language that executes in a runtime environment.  

# Just-In-Time Compilation
Just-In-Time compilation transforms IL into machine-readable instructions at the time of execution.

# References
- [.NET Architectural Components](https://docs.microsoft.com/en-us/dotnet/standard/components)
- [Common Language Infrastructure](https://en.wikipedia.org/wiki/Common_Language_Infrastructure)
- [Common Type System](https://en.wikipedia.org/wiki/Common_Type_System)
- [Tour of .NET](https://docs.microsoft.com/en-us/dotnet/standard/tour)
