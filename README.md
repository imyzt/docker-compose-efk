# docker-compose-efk
This repository is the docker-compose file for EFK

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

