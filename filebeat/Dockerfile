ARG FILEBEAT_VERSION

FROM docker.elastic.co/beats/filebeat:${FILEBEAT_VERSION}

## local vagrant启动虚拟机，挂载目录无法修改权限，使用copy方式
## main 云服务器使用映射

USER root
COPY ./config/filebeat.yml /usr/share/filebeat/filebeat.yml
COPY ./config/modules.d/nginx.yml /usr/share/filebeat/modules.d/nginx.yml
RUN filebeat modules enable nginx \
    && chown root:root /usr/share/filebeat/filebeat.yml \
    && chown root:root /usr/share/filebeat/modules.d/nginx.yml \
