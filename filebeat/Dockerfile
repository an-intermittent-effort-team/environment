ARG FILEBEAT_VERSION

FROM docker.elastic.co/beats/filebeat:${KIBANA_VERSION}
COPY filebeat.yml /usr/share/filebeat/filebeat.yml
USER root
RUN chown root:filebeat /usr/share/filebeat/filebeat.yml
USER filebeat