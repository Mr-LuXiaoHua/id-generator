id-generator
---

###### 项目说明
* 实现请参考 https://github.com/baidu/uid-generator

* 将百度uid-generator组件封装成独立的springboot应用提供服务


####### 目前本项目Snowflake算法的配置如下：

* sign(1bit)  
  固定1bit符号标识，即生成的UID为正数。

* delta seconds (31 bits)  
  当前时间，相对于时间基点"2010-01-01"的增量值，单位：秒，最多可支持约69年

* worker id (19 bits)  
  机器id，最多可支持约52w次机器启动。内置实现为在启动时由数据库分配，默认分配策略为用后即弃。

* sequence (13 bits)   
  每秒下的并发序列，13 bits可支持每秒8192个并发。


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


