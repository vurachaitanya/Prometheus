# Influxdb on a Docker 
- Source link for steps to install and config: https://docs.influxdata.com/influxdb/v1.7/introduction/getting-started/
- Docker command to create a Influxdb :

```
##Build the docker 
docker run -d -p 8086:8086 -v /root/influxdb:/var/lib/influxdb influxdb

## Connect to database
docker exec <Docker ID> -it bash

##Creates Database
create database mydb

##Connects to database
use mydb

##Insert data into cpu and create database
insert cpu,host=serverA,region=us_west value=0.56

Insert <DataBase>,<Tag=Tag Value>,<Tag1=Tag1 Value> <fields=fields_values>,<field1=field1_values>

```

- Conceptually you can think of a measurement as an SQL table, where the primary index is always time. tags and fields are effectively columns in the table. tags are indexed, and fields are not. The difference is that, with InfluxDB, you can have millions of measurements, you don’t have to define schemas up-front, and null values aren’t stored.

```
##Select the cpu databases
select * from cpu

select "host", "region", "value" from "cpu"
select * from temperature limit 1
select * from temperature where time > now() - 1h
```

- Create Database:

```
curl -XPOST http://localhost:8086/query --data-urlencode "q=CREATE DATABASE mydb1"
```

- Inserting into the DB:
```
curl -i -XPOST 'http://localhost:8086/write?db=mydb' --data-binary 'cpu_load_short,host=server01,region=us-west value=0.64 1434055562000000000'
```
