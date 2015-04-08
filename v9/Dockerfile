FROM centos:6.6
MAINTAINER Rodrigo Tsuru <caixapostal@gmail.com>
RUN yum install -y wget 
RUN cd /tmp && wget https://googledrive.com/host/0B1TfHhOuw5TLMWw2YkNITVhWWjQ/9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz
RUN cd /tmp && \
tar -zvxf 9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz && \
rm 9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz
COPY install.rsp /tmp/install.rsp
RUN cd /tmp/messagebroker_runtime1 && \
./installer -r /tmp/install.rsp && \
rm -Rf /tmp/messagebroker_runtime1 
