# docker-compose-efk
This repository is the docker-compose file for EFK

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

