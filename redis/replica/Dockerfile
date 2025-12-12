FROM redis:7.2

# envsubst 설치
RUN apt-get update \
 && apt-get install -y gettext-base \
 && rm -rf /var/lib/apt/lists/*

# 템플릿 복사
COPY redis.conf.template /usr/local/etc/redis/redis.conf.template

# 실행 시 env → conf 렌더링
CMD sh -c "envsubst < /usr/local/etc/redis/redis.conf.template > /usr/local/etc/redis/redis.conf \
 && redis-server /usr/local/etc/redis/redis.conf"
