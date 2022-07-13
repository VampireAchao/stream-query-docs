[![阿超/stream-query](https://gitee.com/VampireAchao/stream-query/widgets/widget_card.svg?colors=4183c4,ffffff,ffffff,e3e9ed,666666,9b9b9b)](https://gitee.com/VampireAchao/stream-query)

[![Maven Central](https://img.shields.io/maven-central/v/io.github.vampireachao/stream-query.svg?label=Maven%20Central)](https://search.maven.org/artifact/io.github.vampireachao/stream-query)
[![stars](https://gitee.com/vampireachao/stream-query/badge/star.svg)](https://gitee.com/VampireAchao/stream-query)
[![stars](https://img.shields.io/github/stars/vampireachao/stream-query.svg?style=social)](https://github.com/VampireAchao/stream-query)
[![LICENSE](https://img.shields.io/badge/license-Apache%202-blue)](https://github.com/VampireAchao/stream-query/blob/master/LICENSE)
[![java8](https://img.shields.io/badge/java-8-blue)](https://docs.oracle.com/javase/8/docs/)

## core包

core包是对于lambda的一些封装，简单介绍:

使用`SerCons.multi`，可以让你的`forEach`支持多个`lambda`操作

```java
import static io.github.vampireachao.stream.core.lambda.function.SerCons.multi;


Arrays.asList("vampire", "a chao").forEach(multi(
        System.out::println,
        System.err::println,
        i -> System.out.println(i.equals("vampire"))
));

```

## plugin包

随着自己日日夜夜的CRUD，我在想，也许是时候抽取、封装一波了

那么就有了这款插件，有了它，你可以将复杂的逻辑，简短表述

曾经我们如果想要根据某字段in或者eq查询列表:

```java
    // SqlHelper来自：https://gitee.com/baomidou/mybatis-plus/blob/3.0/mybatis-plus-extension/src/main/java/com/baomidou/mybatisplus/extension/toolkit/SqlHelper.java
    List<UserInfo> userList = age == null ? new ArrayList<>() : SqlHelper.execute(UserInfo.class, userMapper -> userMapper.selectList(Wrappers.<UserInfo>lambdaQuery().eq(UserInfo::getAge, age)));
```

使用`Many`:

```java
    List<UserInfo> userList = Many.query(age, UserInfo::getAge);
```

有人说，你这样，只能在简单条件用用，复杂条件怎么办呢？

因此query方法提供了重载

```java
    // 这里的w就是LambdaQueryWrapper，此处是查询age = 1L，年龄 <= 20 的用户姓名
    List<String> names = Many.query(w -> w.le(UserInfo::getAge, 20), 1L, UserInfo::getId, UserInfo::getName);    
```
