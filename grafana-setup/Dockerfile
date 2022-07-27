FROM fuww/alpine-curl-ssl-jq

ENV SERVICE_GRAFANA_HOST grafana
ENV SERVICE_GRAFANA_PORT 3000
# ENV SERVICE_GRAFANA_USERNAME "admin"
# ENV SERVICE_GRAFANA_PASSWORD "admin"
GF_AUTH_ANONYMOUS_ORG_ROLE=Admin
GF_AUTH_ANONYMOUS_ENABLED=true
GF_AUTH_BASIC_ENABLED=false
GF_SERVER_SERVE_FROM_SUB_PATH=true

COPY ./startup.sh /usr/bin/startup.sh
RUN chmod +x /usr/bin/startup.sh

RUN mkdir /datasources
COPY ./datasources/*.json /datasources/

RUN mkdir /alert-channels
COPY ./alert-channels/*.json /alert-channels/

RUN mkdir /dashboards
COPY ./dashboards/*.json /dashboards/

CMD ["/usr/bin/startup.sh"]
