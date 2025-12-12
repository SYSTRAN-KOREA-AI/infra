#FROM redis:7.2
#
#COPY redis.conf /usr/local/etc/redis/redis.conf
#
#CMD ["redis-server", "/usr/local/etc/redis/redis.conf"]


FROM redis:7.2

# envsubst 제공
RUN apt-get update && apt-get install -y gettext-base && rm -rf /var/lib/apt/lists/*

# 템플릿 복사
COPY redis.conf.template /usr/local/etc/redis/redis.conf.template

# 실행 시점에 치환 후 Redis 실행
CMD sh -c "envsubst < /usr/local/etc/redis/redis.conf.template > /usr/local/etc/redis/redis.conf && redis-server /usr/local/etc/redis/redis.conf"
