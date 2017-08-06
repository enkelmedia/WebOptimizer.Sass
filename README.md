# A Scss compiler for ASP.NET Core

[![Build status](https://ci.appveyor.com/api/projects/status/i4uo3yef1gpyu00y?svg=true)](https://ci.appveyor.com/project/madskristensen/weboptimizer-sass)

This package compiles Sass/Scss into CSS by hooking into the [LigerShark.WebOptimizer](https://github.com/ligershark/WebOptimizer) pipeline.

Here's an example of how to compile `a.scss` and `b.scss` and bundle them into a single .css file called `/all.css`:

```c#
services.AddWebOptimizer(pipeline =>
{
    pipeline.AddScssBundle("/all.css", "css/a.scss", "css/b.scss");
});
```

You can also reference any .scss files directly and a compiled and minified CSS document will be served. To set that up, do this:

```c#
services.AddWebOptimizer(pipeline =>
{
    pipeline.CompileScssFiles();
});
```

Or if you just want to parse specific markdown files, do this:

```c#
services.AddWebOptimizer(pipeline =>
{
    pipeline.CompileScssFiles("/path/file1.md", "/path/file2.md");
});
```