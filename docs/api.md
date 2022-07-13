## One

> 查询单条记录

最简用法

```java
// 通过 邮箱 等于 "achao1441470436@gmail.com" 查询单条记录
// 对应SQL: select * from user_info where email = "achao1441470436@gmail.com"
UserInfo user = One.query("achao1441470436@gmail.com", UserInfo::getEmail);
```

自行拓展

```java
// 查询 年龄 小于等于20岁 、邮箱 等于 "achao1441470436@gmail.com" 的单条记录，并获取其name
String query = One.query(w -> w.le(UserInfo::getAge, 20),
        "achao1441470436@gmail.com",
        UserInfo::getEmail,
        UserInfo::getName);
```

此处的`w`就是条件构造器,会优先构造`in`条件,`w->null`或者 传入的条件值为`null` 表示不进行查询,返回`null`