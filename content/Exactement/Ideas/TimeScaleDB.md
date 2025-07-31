- docker run -d --name timescaledb -p 5432:5432 -e POSTGRES_PASSWORD=12345 timescale/timescaledb-ha:pg17

son kisim 17 yi pulladigimiz icin 17, yani direk onu calistir diyoruz, komut olarak da

- docker start timescaledb

Table datasini sunduk
postgres=# CREATE TABLE IF NOT EXISTS raw_trade_data (
postgres(# time TIMESTAMP WITH TIME ZONE NOT NULL,
postgres(# symbol text NOT NULL,
postgres(# price double PRECISION NOT NULL,
postgres(# quantity double PRECISION NOT NULL);