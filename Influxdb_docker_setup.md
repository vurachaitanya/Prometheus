# Influxdb on a Docker 
- Source link for steps to install and config: https://docs.influxdata.com/influxdb/v1.7/introduction/getting-started/
- Docker command to create a Influxdb :

```
#Build the docker 
docker run -d -p 8086:8086 -v $PWD:/var/lib/influxdb influxdb
insert cpu,host=serverA,region=us_west value=0.56
select "host", "region", "value" from "cpu"

select * from temperature limit 1

select * from temperature where time > now() - 1h
```
