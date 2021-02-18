ARG FILEBEAT_VERSION

FROM docker.elastic.co/beats/filebeat:${FILEBEAT_VERSION}

## local vagrant启动虚拟机，挂载目录无法修改权限，使用copy方式
## main 云服务器使用映射

USER root
#COPY ./config/filebeat.yml /usr/share/filebeat/filebeat.yml
#COPY ./config/modules.d/nginx.yml /usr/share/filebeat/modules.d/nginx.yml
#RUN chown root:filebeat /usr/share/filebeat/filebeat.yml \
#    && chmod 744 /usr/share/filebeat/filebeat.yml
RUN filebeat modules enable nginx