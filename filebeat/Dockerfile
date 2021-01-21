ARG FILEBEAT_VERSION

FROM docker.elastic.co/beats/filebeat:${FILEBEAT_VERSION}
COPY ./config/filebeat.yml /usr/share/filebeat/filebeat.yml
USER root
RUN chown root:filebeat /usr/share/filebeat/filebeat.yml \
    && chmod 744 /usr/share/filebeat/filebeat.yml
USER filebeat


#RUN chown root:filebeat /usr/share/filebeat/filebeat.yml
#RUN chmod 744 /usr/share/filebeat/filebeat.yml
#RUN chown root:filebeat /usr/share/filebeat/filebeat.yml
#USER filebeat