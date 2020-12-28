# OpenCC-NET

* 此程序是[saviorxzero98/OpenCC-NET](https://github.com/saviorxzero98/OpenCC-NET)的衍生程序，主要进行一些使用上的简化操作。在此向原作者saviorxzero98表示感谢。

### 此版本与原版的不同之处
* 将字典移入DLL内部作为资源，引用时不需要再额外提供字典文件
* 移除了读取文件的代码和FilePathHelper，加载字典已经不再需要这些内容
* 将版本号改为了1.0.1并已经上传到NuGet（在遵守Apache License的前提下）

## Introduction 

* 提供中文簡繁轉換
* 使用由 BYVoid([byvoid.kcp@gmail.com](mailto:byvoid.kcp@gmail.com)) 所開發的 [OpenCC](https://github.com/BYVoid/OpenCC) 中的字典檔案
* 支援 .NET Core 2.0 以上、.NET Framework 4.6.1 以上



## Installation 

* 三种安装方法：
    1. 將 **OpenCC-NET** 專案加入到開發方案 (Solution) 中，並且將專案加入參考 (Reference)
    2. 在此目录下运行dotnet publish -c Release，之后从publish目录取出DLL文件并引用
    3. 在NuGet上搜索安装此库（推荐）

## Usage 



```c#
var converter = new OpenChineseConverter();

// 簡體轉台灣正體
string twText = converter.ToTaiwanFromSimplifiedWithPhrases("这个意大利制造的鼠标");

// 簡體轉香港繁體
string hkText = converter.ToHongKongFromSimplified("这个意大利制造的鼠标");

// 台灣正體轉簡體
string cnText = converter.ToHongKongFromSimplified("這個義大利製造的滑鼠");
```



| Method name                       | Description                  |
| --------------------------------- | ---------------------------- |
| ToTaiwanFromSimplified            | 簡體 → 臺灣正體              |
| ToTaiwanFromSimplifiedWithPhrases | 簡體 → 臺灣正體 (含常用辭彙) |
| ToHongKongFromSimplified          | 簡體 → 香港繁體              |
| ToTraditionalFromSimplified       | 簡體 → 繁體                  |
| ToSimplifiedFromTaiwan            | 臺灣正體 → 簡體              |
| ToSimplifiedFromTaiwanWithPhrases | 臺灣正體 (含常用辭彙) → 簡體 |
| ToSimplifiedFromHongKong          | 香港繁體 → 簡體              |
| ToSimplifiedFromTraditional       | 繁體 → 簡體                  |
| ToTaiwanFromTraditional           | 繁體 → 臺灣正體              |
| ToHongKongFromTraditional         | 繁體 → 香港繁體              |



