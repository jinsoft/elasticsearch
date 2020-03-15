## 索引API

> 请参阅[删除映射类型](https://www.www.com) // Mapping。

将JSON文档添加到指定索引并使其可搜索。如果文档已存在，请更新文档并增加其版本。

###请求

`PUT /<index>/_doc/<_id>`

`POST /<index>/_doc`

`PUT /<index>/_create/<_id>`

`POST /<index>/_create/<_id>`

###路径参数

**`<index>`**

&emsp;&emsp;（必选，字符串）目标索引的名称。默认情况下，如果索引不存在，则会自动创建。
有关更多信息，请参见[自动创建索引](#index-creation)。

**`<_id>`**

&emsp;&emsp;（可选，string）文档的唯一标识符。如果您使用的是PUT请求，则为必填。
省略使用POST请求时自动生成ID的情况。

###查询参数

**``**

&emsp;&emsp;

**``**

&emsp;&emsp;

###请求体

**``**

&emsp;&emsp;

###响应体

**`s`**

&emsp;&emsp;


### <a id="index-creation">自动创建索引</a> 


