## Setting JVM options

此文件包含遵循特殊语法的以行分隔的JVM参数列表

- 空白行被忽略
- 以`#` 开头的行被忽略

```
 # this is a comment
```

- 以`-`开头的行被视为JVM选项，该选项独立于JVM的版本而应用

```
 -Xmx2g
```

- 以数字开头后跟a：后跟a的行被视为JVM选项，仅当JVM的版本与数字匹配时才适用

```
8:-Xmx2g
```
