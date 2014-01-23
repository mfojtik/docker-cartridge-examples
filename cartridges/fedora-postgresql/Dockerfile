FROM goldmann/f20

RUN yum install -y ruby postgresql postgresql-server

RUN mkdir -p /opt/openshift /opt/openshift/conf

ADD ./launch  /opt/openshift/launch
ADD ./prepare /opt/openshift/prepare
ADD ./postgresql.conf.erb /opt/openshift/postgresql.conf.erb

RUN chown -R postgres:postgres /opt/openshift && chmod +x /opt/openshift/*
