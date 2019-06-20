## 安装

Elasticsearch至少需要Java 8，建议您使用Oracle JDK版本1.8.0_131。
Java安装因平台而异，因此我们不会在此处详细介绍。 可以在Oracle的网站上找到Oracle推荐的安装文档。 
在安装Elasticsearch之前，请先运行检查Java版本（然后根据需要进行相应的安装/升级）：

`java -version`

设置了Java之后，就可以下载并运行Elasticsearch。 这些二进制文件可以从[www.elastic.co/downloads](https://www.elastic.co/downloads/)获得，以及过去发布的所有版本。 
对于每个版本，您可以选择zip或tar存档，DEB或RPM包或Windows MSI安装包。

### tar安装

我们按如下方式下载Elasticsearch 6.0.1 tar：

`curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-6.0.1.tar.gz`

提取文件：

> tar -xvf elasticsearch-6.0.1.tar.gz

然后它会在当前目录中创建一堆文件和文件夹。 然后我们进入bin目录，如下所示：

> cd elasticsearch-6.0.1/bin

现在我们准备启动我们的节点和单个集群：

> ./elasticsearch