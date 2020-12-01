

大家好，我们在流程开发时经常会遇到某些组件返回 JSON 格式，需要解析 JSON 格式文件的场景，通过解析 JSON 格式的文本才能获取我们所需的数据。另外 JSON 的格式也很多，很多小伙伴可能在解析JSON上遇到一些困难。那么怎么样才能获取对应的数据呢？本单元介绍如何通过 C# 代码解析 JSON（反序列化）并合理应用在云扩 RPA 编辑器中。

## 什么是JSON

JSON（**J**avaScript **O**bject **N**otation）JavaScript对象表示法， 是存储和交换文本信息的语法。

> **说明：**
>
> -  JSON 基础教程，可参考：https://www.runoob.com/json/json-tutorial.html
> - 在线 JSON 解析及格式化验证网站，可参考：https://www.json.cn/

## JSON 的一般构成

1. JSON 序列化与反序列化

- **JSON 序列化**：将对象转换成JSON 字符串
- **JSON 反序列化**：将JSON 字符串转换成对象

2. JSON 的结构

- **对象结构：{}**

```java
{key1:value1,key2:value2...}
key 的数据类型：字符串value的数据类型：字符串、数值、null、json数组[]、json对象{}
```

- **数组结构：[]**

```
JSON 数组结构：[value1，value2......]
value 的数据类型：字符串、数值、null、json数组[]、json对象{}
```

## JSON 的解析方法

1. C# 代码解析 JSON

可使用 Visual Studio 调试代码，使用 C# 中的 Newtonsoft 库来解析 JSON ，添加引用

```
using Newtonsoft.Json
using Newtonsoft.Json.Linq
```

2. JSON 反序列化语法

```
JsonConvert.DeserializeObject<T>(string value)
```

3. 解析规则

- **针对对象结构{}，使用JObject解析**
- **针对数组结构[]，使用JArray解析**

## JSON 解析案例

### 案例一： 包含一层 JSON 对象

- JSON 文本：

```
{   
"name":"张三",  
"name_en":"zhangssan"
}
```

- 解析代码：

```
string jsonText = "{\"name\":\"张三\",\"name_en\":\"zhangssan\"}";
//解析对象JObject 
JObject jo = (JObject)JsonConvert.DeserializeObject(jsonText);
//获取此对象key="name"和key="name_en"的值
string zone = jo["name"].ToString();
string zone_en = jo["name_en"].ToString();
Console.WriteLine(zone);
Console.WriteLine(zone_en);
```

- 输出：

```
张三
zhangssan
```

### 案例二：包含多层嵌套 JSON 对象解析

- JSON 文本：

```
{  
   "allname":{        
        "name":"张三", 
        "name_en":"zhangsan"
        }
 }
```

解析代码：

```
string jsonText = "{\"allname\":{\"name\":\"张三\",\"name_en\":\"zhangsan\"}}";
//解析对象
JObjectJObject jo = (JObject)JsonConvert.DeserializeObject(jsonText);
//获取此对象中key="allname"下key="name"的值
string zone = jo["allname"]["name"].ToString();
string zone_en = jo["allname"]["name_en"].ToString();
Console.WriteLine(zone);
Console.WriteLine(zone_en);
```

输出：

```
张三
zhangssan
```

### 案例三：JSON 数组解析1（数组循环遍历）

- JSON 文本：

```
[   
    {       
       "a":"a1",     
        "b":"b1"   
     }, 
     {    
        "a":"a2", 
        "b":"b2"   
     }
 ]
```

- 解析代码：

```
string jsonArrayText = "[{\"a\":\"a1\",\"b\":\"b1\"},{\"a\":\"a2\",\"b\":\"b2\"}]"; 
//解析数组JArrayJArray jArray = (JArray)JsonConvert.DeserializeObject(jsonArrayText);
//循环获取数组中的内容
for(int i = 0; i < jArray.Count; i++)
{    
   //解析对象JObject
   JObject j = JObject.Parse(jArray[i].ToString()); 
   //获取此对象key="a"的值
   string a = j["a"].ToString();
   Console.WriteLine(a);
 }
```

- 输出：

```
a1
a2
```

### 案例四：JSON 数组解析2（使用index获取数据）

- JSON 文本：

```
[  
   {    
      "a":"a1",    
      "b":"b1"  
    },
    {  
       "a":"a2", 
       "b":"b2" 
     }
 ]
```

- 解析代码：

```
string jsonArrayText = "[{\"a\":\"a1\",\"b\":\"b1\"},{\"a\":\"a2\",\"b\":\"b2\"}]"; 
//解析数组JArray 
JArray jArray = (JArray)JsonConvert.DeserializeObject(jsonArrayText);
//获取数组jArray中第1个（从第0开始计算）key="a"的值
string str = jArray[1]["a"].ToString();
Console.WriteLine(str);
```

输出：

```
a2
```

### 案例五：JSON 对象中的数组

- JSON 文本：

```
{  
     "name":"网站",  
     "num":3,  
     "sites":[   
         "Google", 
         "Runoob", 
         "Taobao"
         ]
 }
```

- 解析代码：

```
string jsonText = "{\"name\":\"网站\",  \"num\":3,  \"sites\":[\"Google\",\"Runoob\",\"Taobao\"]}";
//解析对象JObjectJObject jo = (JObject)JsonConvert.DeserializeObject(jsonText);
string sites = jo["sites"].ToString();
//解析数组JArrayJArray jArray = (JArray)JsonConvert.DeserializeObject(sites);
//获取数组sites jArray中第0个（从第0开始计算）的值
string sitesdetails = jArray[0].ToString();
Console.WriteLine(sitesdetails);
```

- 输出：

```
Google
```

### 案例六：嵌套 JSON 对象中的数组

- JSON 文本

```
{    
   "name":"网站", 
   "num":2,  
   "sites": [     
       { "name":"Google", "info":[ "Android", "Google 搜索", "Google 翻译" ] },  
       { "name":"Taobao", "info":[ "淘宝", "网购" ] }  
       ]
 }
```

- 解析代码：

```
string jsonText = "{\"name\":\"网站\",\"num\":2,\"sites\":[{\"name\":\"Google\",\"info\":[\"Android\",\"Google搜索\",\"Google翻译\"]},{\"name\":\"Taobao\",\"info\":[\"淘宝\",\"网购\"]}]}";
//解析对象JObject
JObject jo = (JObject)JsonConvert.DeserializeObject(jsonText);
string sites = jo["sites"].ToString();
//解析数组JArray
JArray jArray = (JArray)JsonConvert.DeserializeObject(sites);
//循环遍历sites数组
for (int i = 0; i < jArray.Count; i++)
{  
  //解析对象JObject 
  JObject j = JObject.Parse(jArray[i].ToString()); 
  string info = j["info"].ToString();  
  //解析数组JArray 
  JArray jArray2 = (JArray)JsonConvert.DeserializeObject(info);     //循环遍历info数组
  for (int k = 0; k < jArray2.Count; k++) 
  {   
  Console.WriteLine(jArray2[k]); 
  }
 }
```

- 输出：

```
Android
Google搜索
Google翻译
淘宝
网购
```

## 使用云扩 RPA 编辑器解析 JSON 

**准备工作：**

1. 准备开发流程的电脑，打开云扩学院链接查看云扩 RPA 编辑器运行的硬件&软件要求（https://academy.encoo.com/wiki/Studio/quickStart/HarewareAndSoftwareRequirements.md? ）。

2. 打开云扩官网（https://www.encoo.com/),下载编辑器并安装（本节课使用编辑器版本为：1.1.2010.9）。

3. 准备好 JSON 文本文件。

**操作步骤：**

1. 导入命名空间

```
Newtonsoft.Json
Newtonsoft.Json.Linq
```

![导入命名空间](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/importnamespace20201201.png)

2. 创建项目并拖入**C#代码**组件

![C#组件](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/JSON/Csharp20201201.png)



小结：

1. 解析 JSON 需要对 JSON 的结构进行仔细分析。

2. 掌握解析 JSON 的一些小技巧，比如看到对象使用 JObject，看到数组使用 JArray，嵌套对象解析方法，嵌套对象嵌套数组解析方法，数组循环解析方法，数组使用索引方法解析方法。