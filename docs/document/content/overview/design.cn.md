+++
pre = "<b>1.2 </b>"
title = "设计哲学"
weight = 2
chapter = true
+++

ShardingSphere 采用 Database Plus 设计哲学，该理念致力于构建数据库上层的标准和生态，在生态中补充数据库所缺失的能力。

![Design](https://shardingsphere.apache.org/document/current/img/design_cn.png)

## 连接：打造数据库上层标准

通过对数据库协议、SQL 方言以及数据库存储的灵活适配，快速构建多模异构数据库上层的标准，同时通过内置 DistSQL 为应用提供标准化的连接方式。

## 增强：数据库计算增强引擎

在原生数据库基础能力之上，提供分布式及流量增强方面的能力。前者可突破底层数据库在计算与存储上的瓶颈，后者通过对流量的变形、重定向、治理、鉴权及分析能力提供更为丰富的数据应用增强能力。

## 可插拔：构建数据库功能生态

![ShardingSphere Architecture](https://shardingsphere.apache.org/document/current/img/overview_cn.png)

Apache ShardingSphere 的可插拔架构划分为 3 层，它们是：L1 内核层、L2 功能层、L3 生态层。

### L1 内核层

是数据库基本能力的抽象，其所有组件均必须存在，但具体实现方式可通过可插拔的方式更换。
主要包括查询优化器、分布式事务引擎、分布式执行引擎、权限引擎和调度引擎等。

### L2 功能层

用于提供增量能力，其所有组件均是可选的，可以包含零至多个组件。
组件之间完全隔离，互无感知，多组件可通过叠加的方式相互配合使用。
主要包括数据分片、读写分离、数据库高可用、数据加密、影子库等。
用户自定义功能可完全面向 Apache ShardingSphere 定义的顶层接口进行定制化扩展，而无需改动内核代码。

### L3 生态层

用于对接和融入现有数据库生态，包括数据库协议、SQL 解析器和存储适配器，分别对应于 Apache ShardingSphere 以数据库协议提供服务的方式、SQL 方言操作数据的方式以及对接存储节点的数据库类型。
