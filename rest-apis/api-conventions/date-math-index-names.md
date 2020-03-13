## 索引名称支持日期函数

日期函数索引名称解析使您可以搜索一系列时间序列索引，而不必搜索所有时间序列索引并过滤结果或维护别名。
限制搜索索引的数量可以减少群集上的负载并提高执行性能。
例如，如果您要在日常日志中搜索错误，则可以使用日期函数名称模板将搜索范围限制为过去两天。

几乎所有具有索引参数的API都在索引参数值中支持日期函数。

日期函数索引名称采用以下形式

```
<static_name{date_math_expr{date_format|time_zone}}>
```

`static_name`  &emsp;&emsp; 是名称的静态文本部分 
***
`date_math_expr`  &emsp;&emsp; 是动态日期函数表达式，可动态计算日期
***
`data_format` &emsp;&emsp; 是可选格式，其中应显示计算的日期。默认为yyyy.MM.dd。格式应与Java时间兼容
[https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html)
***
`time_zone`  &emsp;&emsp;是可选的时区。默认为`utc`

日期数学表达式与语言环境无关。因此，除了公历以外，不能使用其他日历。
您必须将日期数学索引名称表达式括在尖括号内，并且所有特殊字符均应使用URI编码。例如：

```
# GET /<logstash-{now/d}>/_search
GET /%3Clogstash-%7Bnow%2Fd%7D%3E/_search
{
  "query" : {
    "match": {
      "test": "data"
    }
  }
}
```

**表达式**  &emsp;&emsp; **解析为**

`<logstash-{now/d}>`  &emsp;&emsp; `logstash-2024.03.22`
***
`<logstash-{now/M}>`  &emsp;&emsp; `logstash-2024.03.01`
***
`<logstash-{now/M{yyyy.MM}}>`  &emsp;&emsp; `logstash-2024.03`
***
`<logstash-{now/M-1M{yyyy.MM}}>`  &emsp;&emsp; `logstash-2024.02`
***
`<logstash-{now/d{yyyy.MM.dd|+12:00}}>`  &emsp;&emsp; `logstash-2024.03.23`