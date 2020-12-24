# Cnblogs.CodeQuality

English | [中文](https://github.com/cnblogs/code-quality/blob/main/README.zh-hans.md)

[![Nuget](https://img.shields.io/nuget/v/Cnblogs.CodeQuality)](https://www.nuget.org/packages/Cnblogs.CodeQuality/)

A bunch of rulesets used by Cnblogs, including StyleCop (`SA-XXXX`) and some other rules (`CA-XXXX`, `IDE-XXXX`, `DOC-XXXX`).

## How to use

If you just want to apply style check in several projects, just install the `Cnblogs.CodeQuality` package on them.

If you want to apply it solution wide, add the code below to your `Directory.Build.props` file.

```xml
<ItemGroup>
  <PackageReference Include="Cnblogs.CodeQuality" Version="1.1.0">
    <PrivateAssets>all</PrivateAssets>
    <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
  </PackageReference>
</ItemGroup>
```

Rebuild you project/solution, `SA-XXXX` warnings or errors (if any) should appeared in your build output.

If you are using Rider or Visual Studio, you may get quick fixes by enable the Roslyn analyzers in your IDE settings.

**Rider Settings:** Editor -> Inspection Settings -> Roslyn Analyzers ([.NET Compiler Platform (Roslyn) Analyzers—JetBrains Rider](https://www.jetbrains.com/help/rider/Using_NET_Compiler_Analyzers.html))
