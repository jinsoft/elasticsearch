## 多个索引

大多数引用索引参数的API都支持使用简单的test1，test2，test3表示法（或对于所有索引为 `_all`）跨多个索引执行。
它还支持通配符，例如：test *或* test或te * t或* test *，以及“排除”（-）的功能，
例如：test *，-test3。

所有多索引API都支持以下url查询字符串参数：

**`ignore_unavailable`**

（可选，布尔值）如果为true，则响应中不包括丢失或闭合的索引。默认为false。

**`allow_no_indices`**

（可选，布尔值）如果为true，则如果通配符表达式或_all值仅检索丢失或闭合的索引，则请求不会返回错误。
此参数还适用于指向别名缺失或封闭索引的索引别名。 

**`expand_wildcards`**

  （可选，字符串）控制通配符表达式可以扩展到的索引类型。有效值为：

&emsp;&emsp;**`all`**

&emsp;&emsp;&emsp;&emsp;展开以打开和关闭索引。

&emsp;&emsp; **`open`**

&emsp;&emsp;&emsp;仅展开以打开索引。

&emsp;&emsp;**`closed`**

&emsp;&emsp;&emsp;&emsp;仅扩展到封闭索引。

&emsp;&emsp;**`none`**

&emsp;&emsp;&emsp;&emsp;不接受通配符表达式。
  
  上述参数的默认设置取决于所使用的API。一些多索引API还支持以下url查询字符串参数：
    
**`ignore_throttled`**

（可选，布尔值）如果为true，则在进行节流时将忽略具体，扩展或别名索引。