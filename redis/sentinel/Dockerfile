FROM redis:7.2

RUN apt-get update \
 && apt-get install -y gettext-base \
 && rm -rf /var/lib/apt/lists/*

COPY sentinel.conf.template /usr/local/etc/redis/sentinel.conf.template

CMD sh -c "envsubst < /usr/local/etc/redis/sentinel.conf.template > /usr/local/etc/redis/sentinel.conf \
 && redis-sentinel /usr/local/etc/redis/sentinel.conf"
