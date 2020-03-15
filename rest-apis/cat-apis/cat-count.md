## cat count API

提供对单个索引或集群中所有索引的文档计数的快速访问。

##**请求**

`GET /_cat/count/<index>`

`GET /_cat/count`

##**路径参数**

**`<index>`**

（可选，string）索引名称的逗号分隔列表或通配符表达式，用于限制请求。

##**查询参数**

**`format`**

&emsp;&emsp;（可选，string）HTTP接受标头的简短版本。有效值包括JSON，YAML等

**`local`**

&emsp;&emsp;（可选，bool）如果为true，则请求仅从本地节点检索信息。
默认为false，表示从主节点检索信息。

**`master_timeout`**

&emsp;&emsp;（可选，时间单位）指定等待连接到主节点的时间段。
如果在超时到期之前未收到任何响应，则请求将失败并返回错误。默认为30秒。

**`h`**

&emsp;&emsp;（可选，string）要显示的以逗号分隔的列名称列表。

**`help`**

&emsp;&emsp;（可选，bool）如果为true，则响应包括帮助信息。默认为false。

**`s`**

&emsp;&emsp;（可选，string）用于对响应进行排序的列名或列别名的逗号分隔列表。v

**`v`**

&emsp;&emsp;（可选，bool）如果为true，则响应包括列标题。默认为false

##**举例**

###**带有单个索引的示例**

以下计数API请求检索单个索引twitter的文档计数。

```
GET /_cat/count/twitter?v
```

API返回以下响应：

```
epoch      timestamp count
1584285615 15:24:20  120
```

###**集群中所有索引的示例**

以下计数API请求检索集群中所有索引的文档计数。

```
GET /_cat/count?v
```

API返回以下响应：

```
epoch      timestamp count
1584285615 15:20:15  0
```