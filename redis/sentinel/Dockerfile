FROM redis:7.2

COPY sentinel.conf /usr/local/etc/redis/sentinel.conf

CMD ["redis-sentinel", "/usr/local/etc/redis/sentinel.conf"]
