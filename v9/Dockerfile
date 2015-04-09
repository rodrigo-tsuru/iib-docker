FROM centos:6.6
MAINTAINER Rodrigo Tsuru <caixapostal@gmail.com>
RUN yum install -y curl \
tar \
glibc.i686
RUN cd /tmp && curl -O -L https://googledrive.com/host/0B1TfHhOuw5TLMWw2YkNITVhWWjQ/9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz
RUN cd /tmp && \
tar -zvxf 9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz && \
rm 9.0.0-IIB-LINUXX64-DEVELOPER-RUNTIME.tar.gz
RUN cd /tmp/integrationbus_developer/WebSphere_MQ && \ 
./mqlicense.sh -accept && \
rm MQSeriesExplorer-7.5.0-3.x86_64.rpm && \
rpm -ivh *.rpm && \
cd /opt/mqm/bin && \
./setmqinst -p /opt/mqm -i
COPY install.rsp /tmp/install.rsp
RUN cd /tmp/integrationbus_developer/ && \
./setuplinuxx64 -i silent -f /tmp/install.rsp && \
rm -Rf /tmp/integrationbus_developer
