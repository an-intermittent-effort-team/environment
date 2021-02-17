ARG FILEBEAT_VERSION

FROM docker.elastic.co/beats/filebeat:${FILEBEAT_VERSION}
#COPY ./config/filebeat.yml /usr/share/filebeat/filebeat.yml
#USER root
#RUN chown root:filebeat /usr/share/filebeat/filebeat.yml \
#    && chmod 744 /usr/share/filebeat/filebeat.yml
#USER filebeat

USER root
COPY ./config/filebeat.yml /usr/share/filebeat/filebeat.yml
COPY ./config/modules.d/nginx.yml /usr/share/filebeat/modules.d/nginx.yml
#RUN chown root:filebeat /usr/share/filebeat/filebeat.yml \
#    && chmod 744 /usr/share/filebeat/filebeat.yml
RUN filebeat modules enable nginx \
    && chown root:root /usr/share/filebeat/filebeat.yml \
    && chown root:root /usr/share/filebeat/modules.d/nginx.yml