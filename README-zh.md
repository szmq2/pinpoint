

![Pinpoint](web/src/main/webapp/images/logo.png)

[![Build Status](https://travis-ci.org/naver/pinpoint.svg?branch=master)](https://travis-ci.org/naver/pinpoint)
[![codecov](https://codecov.io/gh/naver/pinpoint/branch/master/graph/badge.svg)](https://codecov.io/gh/naver/pinpoint)

**访问[我们的官方网站](http://naver.github.io/pinpoint/)获取更多信息以及[Pinpoint最新动态](https://naver.github.io/pinpoint/news.html)**  

## 最新消息 (2018/08/30)

Pinpoint 已开始支持 PHP 编写的应用程序。[查看我们的 php-agent 仓库](https://github.com/naver/pinpoint-c-agent)。

## 最新版本 (2019/03/27)

我们很高兴地宣布 Pinpoint v1.8.3 版本发布。
请在此查看发布说明 (https://github.com/naver/pinpoint/releases/tag/1.8.3)。

当前稳定版本是 [v1.8.3](https://github.com/naver/pinpoint/releases/tag/1.8.3)。

## 关于 Pinpoint

**Pinpoint** 是一个针对用 Java / [PHP](https://github.com/naver/pinpoint-c-agent) 编写的大规模分布式系统的 APM（应用性能管理）工具。
受到 [Dapper](http://research.google.com/pubs/pub36356.html "Google Dapper") 的启发，
Pinpoint 通过跟踪分布式应用程序之间的事务，提供了一个解决方案来帮助分析系统的整体结构以及其中组件之间的相互连接方式。

如果您想要以下功能，一定要试试 **Pinpoint**：

* 一眼了解您的*[应用程序拓扑](https://naver.github.io/pinpoint/overview.html#overview)*
* *实时*监控您的应用程序
* 对每个事务获得*代码级别的可见性*
* 安装 APM 代理*无需更改任何一行代码*
* 对性能的影响最小（资源使用量增加约 3%）

## 快速开始
 * [快速入门指南](https://naver.github.io/pinpoint/1.7.3/quickstart.html) 用于 Pinpoint 的简单测试运行
 * [安装指南](https://naver.github.io/pinpoint/1.7.3/installation.html) 获取更多说明。
 
## 概览
如今的服务通常由许多不同的组件组成，这些组件相互通信并调用外部服务的 API。每个事务的执行过程往往像一个黑盒。Pinpoint 跟踪这些组件之间的事务流，并提供清晰的视图来识别问题区域和潜在的瓶颈。<br/>
如需更详细的介绍，请查看我们的 *[Pinpoint 介绍](http://naver.github.io/pinpoint/#want-a-quick-tour)* 视频片段。

* **服务地图（ServerMap）** - 通过可视化组件之间的相互连接方式来了解任何分布式系统的拓扑结构。点击节点可显示有关组件的详细信息，例如其当前状态和事务计数。
* **实时活动线程图表** - 实时监控应用程序内的活动线程。
* **请求/响应散点图** - 可视化随时间变化的请求计数和响应模式，以识别潜在问题。可以通过**在图表上拖动**来选择事务以获取更多详细信息。

  ![Server Map](doc/images/ss_server-map.png)

* **调用栈（CallStack）** - 在分布式环境中获得对每个事务的代码级可见性，在单个视图中识别瓶颈和故障点。

  ![Call Stack](doc/images/ss_call-stack.png)

* **检查器（Inspector）** - 查看应用程序的其他详细信息，例如 CPU 使用率、内存/垃圾回收、TPS 和 JVM 参数。

  ![Inspector](doc/images/ss_inspector.png)

## 支持的模块
* JDK 6+
* [Tomcat 6/7/8/9](https://github.com/naver/pinpoint/tree/master/plugins/tomcat)，[Jetty 8/9](https://github.com/naver/pinpoint/tree/master/plugins/jetty)，[JBoss EAP 6/7](https://github.com/naver/pinpoint/tree/master/plugins/jboss)，[Resin 4](https://github.com/naver/pinpoint/tree/master/plugins/resin)，[Websphere 6/7/8](https://github.com/naver/pinpoint/tree/master/plugins/websphere)，[Vertx 3.3/3.4/3.5](https://github.com/naver/pinpoint/tree/master/plugins/vertx)，[Weblogic 10/11g/12c](https://github.com/naver/pinpoint/tree/master/plugins/weblogic)，[Undertow](https://github.com/naver/pinpoint/tree/master/plugins/undertow)
* Spring、Spring Boot（嵌入式 Tomcat、Jetty、Undertow）、Spring 异步通信
* Apache HTTP Client 3.x/4.x、JDK HttpConnector、GoogleHttpClient、OkHttpClient、NingAsyncHttpClient、Akka-http、Apache CXF
* Thrift Client、Thrift Service、DUBBO PROVIDER、DUBBO CONSUMER、GRPC
* ActiveMQ、RabbitMQ、Kafka
* MySQL、Oracle、MSSQL(jtds)、CUBRID、POSTGRESQL、MARIA
* Arcus、Memcached、Redis（[Jedis](https://github.com/naver/pinpoint/blob/master/plugins/redis)、[Lettuce](https://github.com/naver/pinpoint/tree/master/plugins/redis-lettuce)）、CASSANDRA、MongoDB、Hbase
* iBATIS、MyBatis
* DBCP、DBCP2、HIKARICP、DRUID
* gson、Jackson、Json Lib、Fastjson
* log4j、Logback

## 兼容性

运行 Pinpoint 所需的 Java 版本：

Pinpoint 版本 | Agent | Collector | Web
---------------- | ----- | --------- | ---
1.0.x | 6-8 | 6-8 | 6-8
1.1.x | 6-8 | 7-8 | 7-8
1.5.x | 6-8 | 7-8 | 7-8
1.6.x | 6-8 | 7-8 | 7-8
1.7.x | 6-8 | 8 | 8
1.8.0 | 6-10 | 8 | 8 
1.8.1+ | 6-11 | 8 | 8 

HBase 兼容性表：

Pinpoint 版本 | HBase 0.94.x | HBase 0.98.x | HBase 1.0.x | HBase 1.2.x | HBase 2.0.x
---------------- | ------------ | ------------ | ----------- | ----------- | -----------
1.0.x | yes | no | no | no | no
1.1.x | no | not tested | yes | not tested | no
1.5.x | no | not tested | yes | not tested | no
1.6.x | no | not tested | not tested | yes | no
1.7.x | no | not tested | not tested | yes | no
1.8.x | no | not tested | not tested | yes | no

Agent - Collector 兼容性表：

Agent 版本 | Collector 1.0.x | Collector 1.1.x | Collector 1.5.x | Collector 1.6.x | Collector 1.7.x | Collector 1.8.x
------------- | --------------- | --------------- | --------------- | --------------- | --------------- | ---------------
1.0.x | yes | yes | yes | yes | yes | yes
1.1.x | not tested | yes | yes | yes | yes | yes
1.5.x | no | no | yes | yes | yes | yes
1.6.x | no | no | not tested | yes | yes | yes
1.7.x | no | no | no | no | yes | yes
1.8.x | no | no | no | no | no | yes

Flink 兼容性表：

Pinpoint 版本 | flink 1.3.X | flink 1.4.X | flink 1.5.X | flink 1.6.X | flink 1.7.X
---------------- | ----------- | ----------- | ----------- | ----------- | ----------- 
1.7.x | yes | yes | no | no | no |
1.8.x | yes | yes | no | no | no |
1.9.x | yes | yes | yes | yes | yes |

## 用户群组
有关问答和讨论，请点击[这里](https://groups.google.com/forum/#!forum/pinpoint_user)。

## 许可证
Pinpoint 根据 Apache License, Version 2.0 授权。
有关完整的许可证文本，请参见 [LICENSE](LICENSE)。

```
Copyright 2018 NAVER Corp.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

