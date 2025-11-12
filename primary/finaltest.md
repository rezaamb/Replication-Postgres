after Doing README.md start this file:

# روی Primary (Node) :
```bash
docker exec -it pg-primary psql -U postgres -d appdb -c \
"CREATE TABLE IF NOT EXISTS customers (firstname TEXT, customer_id SERIAL, date_created TIMESTAMP DEFAULT now());"
```
```bash
docker exec -it pg-primary psql -U postgres -d appdb -c \
"INSERT INTO customers(firstname) VALUES ('REZA');"
```

