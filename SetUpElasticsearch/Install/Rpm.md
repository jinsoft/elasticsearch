## 通过rpm方式安装


### 从rpm源安装

创建 `elasticsearch.repo` 文件,基于RedHat的发行版在 `/etc/yum.repos.d/` 目录下，
或基于OpenSuSE的发行版在 `/etc/zypp/repos.d/` 目录，
内容如下：

```
[elasticsearch-7.x]
name=Elasticsearch repository for 7.x packages
baseurl=https://artifacts.elastic.co/packages/7.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=1
autorefresh=1
type=rpm-md
```

你可以使用以下命令安装：

```
sudo yum install elasticsearch   // CentOS，older RedHat
sudo dnf install elasticsearch   // Fedora和其他较新的Red Hat发行版
sudo zypper install elasticsearch  // OpenSUSE
```

### 手动下载RPM并安装

```
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.1.0-x86_64.rpm
```

> 在基于systemd的发行版上，安装脚本将尝试设置内核参数（例如，vm.max_map_count）; 
您可以通过屏蔽systemd-sysctl.service单元来跳过此步骤。

### 启用自动创建X-Pack 索引

> 如果您使用的是Logstash或Beats，则很可能在action.auto_create_index设置中需要其他索引名称，具体值取决于您的本地配置。
  如果您不确定环境的正确值，可以考虑将值设置为*，这将允许自动创建所有索引。
  
  
### 通过 Sysv `init` 的方式运行 Elasticsearch

```
sudo chkconfig --add elasticsearch
```

如果Elasticsearch因为任何问题没有启动成功，将会打印失败的原因，在日志文件里面可以查看
`/var/log/elasticsearch/`  , 日志文件名为 `/etc/elasticsearch/elasticsearch.yml` 中的 `cluster.name` 名称

### 通过 `systemd` 的方式启动

```
sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable elasticsearch.service
```


### RPM安装的目录结构

Type |  Description  | 	Default Location | Setting
-----|:--------------|:------------------|--------
home | 主目录($ES_HOME)| /usr/share/elasticsearch/|
bin  |启动脚本和安装插件脚本| /usr/share/elasticsearch/bin/|
conf | 配置文件 |  /etc/elasticsearch  | ES_PATH_CONF
data |数据文件位置 | /var/lib/elasticsearch| path.data
logs| 日志文件位置| /var/log/elasticsearch| path.logs 
plugins|插件文件位置 | /usr/share/elasticsearch/plugins/|



















