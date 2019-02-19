# docker-compose-efk
This repository is the docker-compose file for EFK

logstash pipeline&pattern copied from [https://github.com/jieniu/docker-elk](https://github.com/jieniu/docker-elk)

# Setup
1. insert [Docker](docker.com)
2. insert [docker-compose](http://docs.docker.com/compose/install)
3. Clone this repository
4. docker-compose up -d[后台运行]
5. cd filebeat -> ./filebeat -e -c filebeat.yml

# 项目的构成
项目分为五个部分, 以目录结构分开.  
1. `docker-compose.yml` docker-compose的启动项文件.
2. `es` 是ElasticSearch的目录,其中包括数据和日志的持久化路径, 以及它的配置文件.
3. `logstash` 在`EFK`系统中担任日志收集系统, 在传统的`ELK`架构中, 开启多个logstash造成了很大的系统资源浪费.
4. `kibana` ElasticSearch的可视化界面
5. `filebeat` 是直接在filebeat仓库下载下来的, 其中`filebeat.yml`是配置的日志收集器.

# 系统架构图
> 不严谨, 目前还未集成kafka

![EFK系统架构图](http://ww1.sinaimg.cn/large/005SWfHCgy1g0bpcrqw6ej30q20dx751.jpg)

# EFK介绍
> 引用自[ELK 架构之 Elasticsearch 和 Kibana 安装配置](https://www.cnblogs.com/xishuai/p/elk-elasticsearch-kibana.html), 这是一篇非常不错的ELK搭建教程, 很多内容都是从中学习的.  

- Elasticsearch 是个开源分布式搜索引擎，提供搜集、分析、存储数据三大功能。它的特点有：分布式，零配置，自动发现，索引自动分片，索引副本机制，restful 风格接口，多数据源，自动搜索负载等。详细可参考 Elasticsearch 权威指南

- Logstash 主要是用来日志的搜集、分析、过滤日志的工具，支持大量的数据获取方式。一般工作方式为 c/s 架构，client 端安装在需要收集日志的主机上，server 端负责将收到的各节点日志进行过滤、修改等操作在一并发往 Elasticsearch 上去。

- Kibana 也是一个开源和免费的工具，Kibana 可以为 Logstash 和 ElasticSearch 提供的日志分析友好的 Web 界面，可以帮助汇总、分析和搜索重要数据日志。

- Beats 在这里是一个轻量级日志采集器，其实 Beats 家族有 6 个成员，早期的 ELK 架构中使用 Logstash 收集、解析日志，但是 Logstash 对内存、cpu、io 等资源消耗比较高。相比 Logstash，Beats 所占系统的 CPU 和内存几乎可以忽略不计。

# 整体流程
系统采用ElasticSearch作为日志搜索引擎, 提供日志搜集,分析和存储 ->   
Logstash做日志的分析和过滤工具 ->   
Kibana 作为日志分析的可视化界面 ->   
其中三者均已整合`docker-compose`, 可以一键启动. logstash监听主机的`10515`端口 ->   
filebeat作为真正的日志搜集工具, 可以监听日志文件或作为日志接收方接收log4j等工具通过TCP发送的日志流. 然后将日志发送至logstash. 






