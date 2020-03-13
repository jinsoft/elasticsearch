## cat APIs

**简介**

JSON非常适合计算机使用。即使打印精美，尝试在数据中查找关系也很繁琐。
人眼，尤其是在看终端时，需要紧凑且对齐的文本。cat API旨在满足这一需求。

> cat API仅适用于使用Kibana控制台或命令行供人类使用。它们不适合应用程序使用。对于应用程序消耗，我们建议使用相应的JSON API。

所有的cat命令都接受查询字符串参数帮助，以查看它们提供的所有标题和信息，并且/_cat命令仅列出所有可用的命令。

###**常用参数**

####**Verbose**
每个命令都接受查询字符串参数v以打开详细输出。例如：

`GET /_cat/master?v`

可能会回应：

```
id                     host      ip        node
6TJWXMDAQyOwsq3iKUY3IB 127.0.0.1 127.0.0.1 node-1
```

####**help**

`GET /_cat/master?help`

可能会回应：

```
id   |   | node id    
host | h | host name  
ip   |   | ip address 
node | n | node name
```

####**Headers**

每个命令都接受查询字符串参数h，该参数仅强制出现这些列。例如：

`GET /_cat/nodes?h=ip,port,heapPercent,name`

可能会回应：

```
127.0.0.1 9300 31 node-1
```

