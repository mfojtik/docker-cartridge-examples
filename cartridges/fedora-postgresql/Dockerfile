FROM goldmann/f20

RUN yum install -y postgresql postgresql-server

RUN mkdir -p /opt/openshift /opt/openshift/conf

ADD ./prepare /opt/openshift/prepare
ADD ./launch  /opt/openshift/launch
ADD ./postgresql.conf.erb /opt/openshift/postgresql.conf.erb

RUN chown -R postgres:postgres /opt/openshift && chmod +x /opt/openshift/*
