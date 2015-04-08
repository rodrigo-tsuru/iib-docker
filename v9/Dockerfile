FROM centos:6.6
MAINTAINER Rodrigo Tsuru <caixapostal@gmail.com>
RUN yum install -y wget \
tar 
RUN cd /tmp && wget https://googledrive.com/host/0B1TfHhOuw5TLMWw2YkNITVhWWjQ/9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz
RUN cd /tmp && \
tar -zvxf 9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz && \
rm 9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz
RUN integrationbus_developer/WebSphere_MQ/mqlicense.sh -accept && \
yes | rpm -ivh integrationbus_developer/WebSphere_MQ/*.rpm
COPY install.rsp /tmp/install.rsp
RUN cd /tmp/integrationbus_developer/ && \
./setuplinuxx64 -f /tmp/install.rsp && \
rm -Rf /tmp/integrationbus_developer
