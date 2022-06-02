### 安装

核心依赖，可单独作为工具包使用

<!-- tabs:start -->

#### **Maven**

```xml
<!-- https://search.maven.org/artifact/io.github.vampireachao/stream-query -->
<dependency>
    <groupId>io.github.vampireachao</groupId>
    <artifactId>stream-core</artifactId>
    <version>1.0.6</version>
</dependency>
```

#### **Gradle**

```gradle
// https://search.maven.org/artifact/io.github.vampireachao/stream-query
implementation group: 'io.github.vampireachao', name: 'stream-plugin-mybatis-plus', version: '1.0.6'
```

<!-- tabs:end -->


`orm`插件，目前支持`mybatis-plus`

<!-- tabs:start -->

#### **Maven**

```xml
<!-- https://search.maven.org/artifact/io.github.vampireachao/stream-query -->
<dependency>
    <groupId>io.github.vampireachao</groupId>
    <artifactId>stream-plugin-mybatis-plus</artifactId>
    <version>1</version>
</dependency>
```

#### **Gradle**

```gradle
// https://search.maven.org/artifact/io.github.vampireachao/stream-query
implementation group: 'io.github.vampireachao', name: 'stream-core', version: '1.0.6'
```

<!-- tabs:end -->

### 使用

[查看测试用例](https://gitee.com/VampireAchao/stream-query/blob/master/stream-plugin/stream-plugin-mybatis-plus/src/test/java/io/github/vampireachao/stream/plugin/mybatisplus/OneToOneTest.java ':type=iframe width=100% height=400px')
