# OneForAll.FF.File
.NET Framework 框架文件类库

## 简介
OneForAll.FF.File 是专为 .NET Framework 环境设计的核心工具库，提供通用的文件操作帮助类等，适用于 ASP.NET、WinForms、WPF 等 .NET Framework 项目。

## 注意：仅限 .NET Framework
本库仅支持 .NET Framework 4.6.2 及以上版本。  
如需 .NET Core 版本，请使用：
https://www.nuget.org/packages/OneForAll.File/

## 使用示例
1. FileHelper：基础操作
```C#
// 创建空白文件
FileHelper.Create(string filePath)
// 写入
FileHelper.Write(string filePath, Stream stream)
// 读取
FileHelper.ReadStream(string filePath, Stream stream)
// 移动
FileHelper.Move(string source, string target)
// 复制
FileHelper.Copy(string source, string target, bool deleteSource = false, bool overWrite = true)
// 获取文件信息
FileHelper.GetList(string path)
```
2. TextHelper：文本文件操作
```C#
// 创建空白文件
TextHelper.Create(string fileName, bool recover)
// 写入
TextHelper.Write(string fileName, string content)
// 读取
TextHelper.Read(string path, Encoding encoding = null)
```
3. DirectoryHelper：目录操作
```C#
// 创建
DirectoryHelper.Create(string path)
// 移动
DirectoryHelper.Move(string sourceDir, string targetDir)
// 移动文件
DirectoryHelper.MoveFiles(string directorySource, string directoryTarget, SearchOption option)
// 复制
DirectoryHelper.Copy(string source, string target)
```
4. Uploader：文件上传器
```C#
await new Uploader().WriteAsync(Stream fileStream, string path, string fileName, bool autoName = false, int maxSize = 0)
```
5. NPOIExcelHelper：基于NPOI的Excel文件操作
```C#
// 导出
NPOIExcelHelper.Export(List<DataTable> dts, FileType type, string filePath, int[] noWriteColumns = null, bool isWriteColumnHeader = false)
// 导入
NPOIExcelHelper.Import<T>(string filePath)
NPOIExcelHelper.Import(Stream stream, FileType type=FileType.xlsx, bool isFirstTitle = false)
```

## 许可证
MIT License