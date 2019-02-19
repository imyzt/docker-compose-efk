# docker-compose-efk
This repository is the docker-compose file for EFK

logstash pipeline&pattern copied from [https://github.com/jieniu/docker-elk](https://github.com/jieniu/docker-elk)

# Setup
1. insert [Docker](docker.com)
2. insert [docker-compose](http://docs.docker.com/compose/install)
3. Clone this repository
4. docker-compose up -d[��̨����]
5. cd filebeat -> ./filebeat -e -c filebeat.yml

# ��Ŀ�Ĺ���
��Ŀ��Ϊ�������, ��Ŀ¼�ṹ�ֿ�.  
1. `docker-compose.yml` docker-compose���������ļ�.
2. `es` ��ElasticSearch��Ŀ¼,���а������ݺ���־�ĳ־û�·��, �Լ����������ļ�.
3. `logstash` ��`EFK`ϵͳ�е�����־�ռ�ϵͳ, �ڴ�ͳ��`ELK`�ܹ���, �������logstash����˺ܴ��ϵͳ��Դ�˷�.
4. `kibana` ElasticSearch�Ŀ��ӻ�����
5. `filebeat` ��ֱ����filebeat�ֿ�����������, ����`filebeat.yml`�����õ���־�ռ���.

# ϵͳ�ܹ�ͼ
> ���Ͻ�, Ŀǰ��δ����kafka

![EFKϵͳ�ܹ�ͼ](http://ww1.sinaimg.cn/large/005SWfHCgy1g0bpcrqw6ej30q20dx751.jpg)

# EFK����
> ������[ELK �ܹ�֮ Elasticsearch �� Kibana ��װ����](https://www.cnblogs.com/xishuai/p/elk-elasticsearch-kibana.html), ����һƪ�ǳ������ELK��̳�, �ܶ����ݶ��Ǵ���ѧϰ��.  

- Elasticsearch �Ǹ���Դ�ֲ�ʽ�������棬�ṩ�Ѽ����������洢���������ܡ������ص��У��ֲ�ʽ�������ã��Զ����֣������Զ���Ƭ�������������ƣ�restful ���ӿڣ�������Դ���Զ��������صȡ���ϸ�ɲο� Elasticsearch Ȩ��ָ��

- Logstash ��Ҫ��������־���Ѽ���������������־�Ĺ��ߣ�֧�ִ��������ݻ�ȡ��ʽ��һ�㹤����ʽΪ c/s �ܹ���client �˰�װ����Ҫ�ռ���־�������ϣ�server �˸����յ��ĸ��ڵ���־���й��ˡ��޸ĵȲ�����һ������ Elasticsearch ��ȥ��

- Kibana Ҳ��һ����Դ����ѵĹ��ߣ�Kibana ����Ϊ Logstash �� ElasticSearch �ṩ����־�����Ѻõ� Web ���棬���԰������ܡ�������������Ҫ������־��

- Beats ��������һ����������־�ɼ�������ʵ Beats ������ 6 ����Ա�����ڵ� ELK �ܹ���ʹ�� Logstash �ռ���������־������ Logstash ���ڴ桢cpu��io ����Դ���ıȽϸߡ���� Logstash��Beats ��ռϵͳ�� CPU ���ڴ漸�����Ժ��Բ��ơ�

# ��������
ϵͳ����ElasticSearch��Ϊ��־��������, �ṩ��־�Ѽ�,�����ʹ洢 ->   
Logstash����־�ķ����͹��˹��� ->   
Kibana ��Ϊ��־�����Ŀ��ӻ����� ->   
�������߾�������`docker-compose`, ����һ������. logstash����������`10515`�˿� ->   
filebeat��Ϊ��������־�Ѽ�����, ���Լ�����־�ļ�����Ϊ��־���շ�����log4j�ȹ���ͨ��TCP���͵���־��. Ȼ����־������logstash. 






