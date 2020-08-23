# Graphite stack

# Build from Ubuntu base
FROM graphiteapp/graphite-statsd

# This suppresses a bunch of annoying warnings from debconf
#ENV DEBIAN_FRONTEND noninteractive
# Graphite
COPY carbon.conf /opt/graphite/conf/carbon.conf
COPY storage-schemas.conf /opt/graphite/conf/storage-schemas.conf
COPY storage-aggregation.conf /opt/graphite/conf/storage-aggregation.conf
# Supervisord
#COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
# StatsD
#COPY statsd_config.js /etc/statsd/config.js
# Graphite API
COPY graphite-api.yaml /etc/graphite-api.yaml
# uwsgi
#COPY uwsgi.conf /etc/uwsgi.conf
# nginx
#COPY nginx.conf /etc/nginx/nginx.conf
#COPY basic_auth /etc/nginx/basic_auth

# nginx
EXPOSE 80 \
# graphite-api
8080 \
# Carbon line receiver
2003 \
# Carbon pickle receiver
2004 \
# Carbon cache query
7002 \
# StatsD UDP
8125 \
# StatsD Admin
8126

RUN apk add bash

# Launch stack
#CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf"]
