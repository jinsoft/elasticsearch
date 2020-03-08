## 配置Elasticsearch

Elasticsearch具有良好的默认值，只需要很少的配置。 可以使用 Cluster Update Settings API在正在运行的群集上更改大多数设置。
配置文件应包含特定于节点的设置（例如`node.name`和`paths`），或节点为了能够加入集群而需要的设置，
例如`cluster.name`和`network.host`。

### 配置文件位置

Elasticsearch有3个配置文件:
- `elasticsearch.yml` 用于配置Elasticsearch
- `jvm.options` 用于配置Elasticsearch JVM
- `log4j2.properties` 用于配置Elasticsearch日志


