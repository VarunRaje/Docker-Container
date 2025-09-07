```
docker run -d \
      --name redis \
      -p 6379:6379 \
      -v redis.conf:/usr/local/etc/redis/redis.conf \
      redis redis-server /usr/local/etc/redis/redis.conf
```
