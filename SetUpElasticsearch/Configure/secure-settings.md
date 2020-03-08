## 安全设置

某些设置是敏感的，依靠文件系统权限来保护其值是不够的。 
对于此用例，Elasticsearch提供了一个密钥库和`elasticsearch-keystore`工具来管理密钥库中的设置。

> 此处的所有命令都应该作为运行Elasticsearch的用户运行。

> 只有一些设置可以从密钥库中读取。 请参阅每个设置的文档，以查看它是否作为密钥库的一部分受支持。

> 只有在重新启动Elasticsearch之后，对密钥库的所有修改才会生效

这些设置与elasticsearch.yml配置文件中的常规设置一样，需要在集群中的每个节点上指定。
目前，所有安全设置都是特定于节点的设置，每个节点上的值必须相同。

### 创建秘钥

要创建 `elasticsearch.keystore`, 使用`create` 命令

```
bin/elasticsearch-keystore create
```