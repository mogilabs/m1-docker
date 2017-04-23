FROM centos/httpd:latest

# Update apt-get and install a few things
RUN yum -y --setopt=tsflags=nodocs update && \
    yum -y --setopt=tsflags=nodocs install mod_ssl && \
    yum clean all

EXPOSE 443