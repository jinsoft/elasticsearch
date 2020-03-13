## 基于URL的访问控制

许多用户使用具有基于URL的访问控制的代理来保护对Elasticsearch索引的访问。
对于多搜索，多获取和批量请求，用户可以选择在URL以及请求正文中的每个单独请求上指定索引。
这会使基于URL的访问控制具有挑战性。

为了防止用户覆盖URL中指定的索引，请将此设置添加到elasticsearch.yml文件中：

`rest.action.multi.allow_explicit_index: false`

默认值为`true`，但是当设置为`false`时，Elasticsearch将拒绝在请求正文中具有显式索引的请求。