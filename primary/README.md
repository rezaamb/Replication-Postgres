# بالا آوردن
```
cd /opt/pg-ha/primary
```
```
docker compose up -d
```
```
docker logs -f pg-primary
```
# اگر role هنگام init ساخته نشده بود:
```bash
docker exec -it pg-primary psql -U postgres -c \
"DO $$BEGIN
  IF NOT EXISTS (SELECT 1 FROM pg_roles WHERE rolname='admin') THEN
    CREATE ROLE admin WITH REPLICATION LOGIN PASSWORD 'admin';
  ELSE
    ALTER ROLE admin WITH REPLICATION LOGIN PASSWORD 'admin';
  END IF;
END$$;"
```

# پس از هر ویرایش در pg_hba.conf یا postgresql.conf:
```bash
docker exec -it pg-primary psql -U postgres -c "SELECT pg_reload_conf();"
```

# اگر appdb ساخته نشده بود:
```bash
docker exec -it pg-primary psql -U postgres -d postgres -c "CREATE DATABASE appdb;"
```
