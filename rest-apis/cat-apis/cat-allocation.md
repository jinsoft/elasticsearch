## cat allocation API

提供分配给每个数据节点的分片数量及其磁盘空间的快照。

##**请求**

`GET /_cat/allocation/<node_id>`

`GET /_cat/allocation`

##**路径参数**

**`<node_id>`**

（可选，string）节点ID或名称的逗号分隔列表，用于限制返回的信息。

##**查询参数**

**`bytes`**

&emsp;&emsp;（可选，字节大小单位）用于显示字节值的单位

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

```
GET /_cat/allocation?v
```


API返回以下响应：

```
shards disk.indices disk.used disk.avail disk.total disk.percent host      ip        node
     0           0b     3.4gb     32.1gb     35.5gb            9 127.0.0.1 127.0.0.1 node-1
```