## Check status
```bash
systemctl status zookeeper-server
```
## Restart
```bash
sudo systemctl restart zookeeper-server
```
## Stop
```bash
sudo systemctl stop zookeeper-server
```
## Start
```bash
sudo systemctl start zookeeper-server
```
## Check if node is leader or follower
```bash
echo stat | nc localhost 2181 | grep Mode
```
## Check connection logs
Connection logs:
```bash
sudo cat /var/log/messages | tail -50 # Verify log timestamps
```
## View node config
```bash
cat /etc/zookeeper/conf/zoo.cfg
```
## Run Zookeeper
```bash
/usr/lib/zookeeper/bin/zkCli.sh
```

List the clients using Zookeeper:
```bash
ls /
```

List Kafka topics known to Zookeeper:
```bash
ls /kafka/kafkacluster/brokers/topics
```

List Broker ID's known to Zookeeper:
```bash
ls /kafka/kafkacluster/brokers/ids
```