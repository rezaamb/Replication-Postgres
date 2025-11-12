# حتماً قبل از اولین start دیتادیر را خالی کن تا basebackup بگیرد (اختیاری ولی توصیه‌شده):

docker compose stop
docker run --rm -v replica_pg_data_replica:/var/lib/postgresql/data alpine sh -lc 'rm -rf /var/lib/postgresql/data/*'


# بالا آوردن
```
cd /opt/pg-ha/replica
```
```
docker compose up -d
```
```
docker logs -f pg-replica
```
