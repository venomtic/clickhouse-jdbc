[![clickhouse-jdbc](https://maven-badges.herokuapp.com/maven-central/ru.yandex.clickhouse/clickhouse-jdbc/badge.svg)](https://maven-badges.herokuapp.com/maven-central/ru.yandex.clickhouse/clickhouse-jdbc) [![Build Status](https://travis-ci.org/yandex/clickhouse-jdbc.svg?branch=master)](https://travis-ci.org/yandex/clickhouse-jdbc)
ClickHouse JDBC driver
===============

**由于官方驱动中，高并发情况下会无限创建http连接，导致错误，因此使用http连接池进行控制**

This is a basic and restricted implementation of jdbc driver for ClickHouse.
It has support of a minimal subset of features to be usable.

### Usage
> 重新编译后从私有仓库中引入
```xml
<dependency>
    <groupId>ru.yandex.clickhouse</groupId>
    <artifactId>clickhouse-jdbc</artifactId>
    <version>0.1-SNAPSHOT</version>
</dependency>
```

URL syntax: 
`jdbc:clickhouse://<host>:<port>[/<database>]`, e.g. `jdbc:clickhouse://localhost:8123/test`

JDBC Driver Class:
`ru.yandex.clickhouse.ClickHouseDriver`

additionally, if you have a few instances, you can use `BalancedClickhouseDataSource`.

### Compiling with maven
The driver is built with maven.
`mvn package -DskipTests=true`

To build a jar with dependencies use

`mvn package assembly:single -DskipTests=true`

### Build requirements
In order to build the jdbc client one need to have jdk 1.6 or higher.
