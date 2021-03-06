# Kafka的使用场景

## 一、概述

kafka更好的替换传统的消息系统，消息系统被用于各种场景（解耦数据生产者，缓存未处理的消息，等），与大多数消息系统比较，kafka有更好的吞吐量，内置分区，副本和故障转移，这有利于处理大规模的消息。

根据我们的经验，消息往往用于较低的吞吐量，但需要低的端到端延迟，并需要提供强大的耐用性的保证。

在这一领域的kafka比得上传统的消息系统，如的ActiveMQ或RabbitMQ的

## 二、数据总线 Kafka

最初由 Linkedin 研发并在其内部大规模成功应用，然后在 Apache 上开源的 Kafka，是业内数据总线 (Databus) 一块的标配，几乎每一家互联网公司都可以看到 Kafka 的身影。Kafka 堪称开源项目的一个经典成功案例，其创始人团队从 Linkedin 离职后还专门成立了一家叫 confluent 的企业软件服务公司，围绕 Kafka 周边提供配套和增值服务。在监控一块，日志和 Metrics 等数据可以通过 Kafka 做收集、存储和转发，相当于中间增加了一个大容量缓冲，能够应对海量日志数据的场景。除了日志监控数据收集，Kafka 在业务大数据分析，IoT 等场景都有广泛应用。如果对 Kafka 进行适当定制增强，还可以用于传统消息中间件场景。

Kafka 的特性是大容量，高吞吐，高可用，数据可重复消费，可水平扩展，支持消费者组等。Kafka 尤其适用于不严格要求实时和不丢数据的大数据日志场景。

Kafka 创始人三人组，离开 Linkedin 后，创立了基于 Kafka 的创业公司 Confluent。



## 三、网站活动追踪

kafka原本的使用场景：用户的活动追踪，网站的活动（网页游览，搜索或其他用户的操作信息）发布到不同的话题中心，这些消息可实时处理，实时监测，也可加载到Hadoop或离线处理数据仓库。

每个用户页面视图都会产生非常高的量。

## 四、指标

kafka也常常用于监测数据。分布式应用程序生成的统计数据集中聚合


## 五、日志聚合

使用kafka代替一个日志聚合的解决方案。

## 六、流处理

kafka消息处理包含多个阶段。其中原始输入数据是从kafka主题消费的，然后汇总，丰富，或者以其他的方式处理转化为新主题，例如，一个推荐新闻文章，文章内容可能从“articles”主题获取；然后进一步处理内容，得到一个处理后的新内容，最后推荐给用户。这种处理是基于单个主题的实时数据流。从0.10.0.0开始，轻量，但功能强大的流处理，就进行这样的数据处理了。

除了Kafka Streams，还有Apache Storm和Apache Samza可选择。

## 七、事件采集

事件采集是一种应用程序的设计风格，其中状态的变化根据时间的顺序记录下来，kafka支持这种非常大的存储日志数据的场景。

## 八、提交日志

kafka可以作为一种分布式的外部提交日志，日志帮助节点之间复制数据，并作为失败的节点来恢复数据重新同步，kafka的日志压缩功能很好的支持这种用法，这种用法类似于Apacha BookKeeper项目。


