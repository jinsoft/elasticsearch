## 查询DSL

Elasticsearch提供了基于JSON的完整查询DSL（特定于域的语言）来定义查询。
将查询DSL视为查询的AST（抽象语法树），由两种类型的子句组成

#### 叶子查询子句

叶子查询子句在特定字段中查找特定值，例如[`match`](https://www.xxx.com)，[`term`](https://www.xxx.com)或[`range`](https://www.xxx.com)查询。这些查询可以自己使用。

#### 复合查询子句

复合查询子句包装其他叶查询或复合查询，并用于以逻辑方式组合多个查询（例如[`bool`](https://www.xxx.com)或[`dis_max`](https://www.xxx.com)查询），
或更改其行为（例如[`constant_score`](https://www.xxx.com)查询）。

查询子句的行为会有所不同，具体取决于它们是在[`查询上下文中还是在过滤器上下文中`](query-dsl/query-filter-context.md)使****用。