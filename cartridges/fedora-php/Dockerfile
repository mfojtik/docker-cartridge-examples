FROM goldmann/f20

RUN yum install -y ruby httpd php php-common php-pecl-apc php-cli php-pear php-pdo php-mysqlnd php-pgsql php-pecl-mongo php-pecl-memcache php-pecl-memcached php-gd php-mbstring php-mcrypt php-xml

RUN mkdir -p /opt/openshift && \
  groupadd -r php_app -g 433 && \
  useradd -u 431 -r -g php_app -d /opt/openshift -s /sbin/nologin -c "php app user" php_app

ADD ./prepare /opt/openshift/prepare
ADD ./launch  /opt/openshift/launch
ADD ./httpd.conf.erb /opt/openshift/httpd.conf.erb

RUN chown -R php_app:php_app /opt/openshift && chmod +x /opt/openshift/*
