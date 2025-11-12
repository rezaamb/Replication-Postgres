after Doing README.md start this file:
# روی Replica (nri) :
```bash
docker exec -it pg-replica psql -U postgres -d appdb -c "SELECT * FROM customers;"
```
# Check Stream
```bash
docker exec -it pg-replica psql -U postgres -d postgres -c \
"SELECT status, receive_start_lsn, latest_end_lsn FROM pg_stat_wal_receiver;"
```
