# Redis Slave Connectivity Check

### Description
```
This plugin was written to get it a slave redis is really connected properly to master server.
```

### Usage
```
python check_redis_slave.py -h
Usage: check_redis_slave.py [options]

Options:
  -h, --help  show this help message and exit
  -H HOST     Slave redis host address
  -P PORT     Redis tcp port, default 6379

```
 
### Sample Plugin Output
```
[ugur@test]# python check_redis_slave.py -H <slave-redis-host> -P 6383
OK: slave redis is connected properly to master|master_last_io_seconds_ago=4;0;0;0

If slave connectivty was broken due to some reasons that it raised an alert.

[ugur@test]# python check_redis_slave.py -H <slave-redis-host> -P 6383
Critical: slave redis server is failed to connect master.It is down!
```

### Tested with 
```
Icinga2 + Redis 2.8.19 - Redis 3.2.1 Cluster
I think that it should be fine with the nagios based software.
```
