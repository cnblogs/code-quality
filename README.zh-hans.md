# Cnblogs.CodeQuality

[English](https://github.com/cnblogs/code-quality/blob/main/README.md) | 中文

[![Nuget](https://img.shields.io/nuget/v/Cnblogs.CodeQuality)](https://www.nuget.org/packages/Cnblogs.CodeQuality/)

博客园开源项目使用的 Roslyn 分析器规则集，包括 StyleCop (`SA-XXXX`) 及其他的一些规则 (`CA-XXXX`, `IDE-XXXX`, `DOC-XXXX`)。

## 如何使用

如果只需要对少数项目启用，直接在这些项目上安装 `Cnblogs.CodeQuality` 包即可。

如果希望对整个解决方案或者目录启用，在 `Directory.Build.props` 文件中添加如下代码。

```xml
<ItemGroup>
  <PackageReference Include="Cnblogs.CodeQuality" Version="1.1.0">
    <PrivateAssets>all</PrivateAssets>
    <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
  </PackageReference>
</ItemGroup>
```

重新编译后应该就可以在输出中看到分析器给出的 Warning 和 Error 了。

如果你使用 Rider 或者 Visual Studio，IDE 还会给出这些问题的快速修复，VS 默认开启分析，Rider 可以通过下面的路径找到 Roslyn 分析器设置。

**Rider:** Editor -> Inspection Settings -> Roslyn Analyzers ([.NET Compiler Platform (Roslyn) Analyzers—JetBrains Rider](https://www.jetbrains.com/help/rider/Using_NET_Compiler_Analyzers.html))
