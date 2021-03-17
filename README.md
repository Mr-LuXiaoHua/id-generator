id-generator
---

###### 项目说明
* 实现请参考 https://github.com/baidu/uid-generator

* 将百度uid-generator组件封装成独立的springboot应用提供服务

###### 使用方法
1. 修改application.properties，配置好数据库
2. 执行 doc/init.sql 初始化表
3. 运行springboot项目

###### 接口调用
```
1. 获取单个id: http://localhost:9999/getNextId

2. 批量获取id: http://localhost:9999/getNextIds?num=10    0 < num <= 100

3. 解析id: http://localhost:9999/parseId?id=

```


