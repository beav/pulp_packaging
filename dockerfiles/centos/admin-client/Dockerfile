FROM centos:centos7
MAINTAINER Pulp Team <pulp-list@redhat.com>

ADD rhel-pulp.repo /etc/yum.repos.d/rhel-pulp.repo

RUN yum install -y epel-release && yum clean all

RUN  yum update -y && \
     yum groupinstall -y \
         pulp-admin && \
     yum install -y \
         pulp-docker-admin-extensions && \
     yum clean all

# config and uploads dir
VOLUME ["/.pulp /run/pulp_uploads"]

ADD admin.conf /root/.pulp/admin.conf
