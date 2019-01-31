# redis主从

```bash
# 拉取redis
docker pull redis

# 目录
├── docker-compose.yml
├── master
│   ├── Dockerfile
│   └── redis.conf
├── redis.conf
├── slave1
│   ├── Dockerfile
│   └── redis.conf
└── slave2
    ├── Dockerfile
    └── redis.conf

# 启动
docker-compose up -d master slave1 slave2

# 查看主容器
docker-compose exec master bash
root@cab5db8d544b:/data# redis-cli
127.0.0.1:6379> info Replication
# Replication
role:master
connected_slaves:2
slave0:ip=172.23.0.3,port=6379,state=online,offset=1043,lag=0
slave1:ip=172.23.0.4,port=6379,state=online,offset=1043,lag=0
master_replid:995257c6b5ac62f7908cc2c7bb770f2f17b60401
master_replid2:0000000000000000000000000000000000000000
master_repl_offset:1043
second_repl_offset:-1
repl_backlog_active:1
repl_backlog_size:1048576
repl_backlog_first_byte_offset:1
repl_backlog_histlen:1043

```