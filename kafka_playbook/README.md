# How to setup
1. Edit your hosts
   1. Kafka nodes  (min 2 nodes)
   2. Zookeeper nodes -> you can use the same nodes as Kafka (min 2 nodes)

2. "remote_user" in the kafka.yaml file. I have used user "ubuntu". 

3. For each "kafka" and "zookeeper-nodes" have a unique "kafka_broker_id" and "zookeeper_id" ids

4. Run playbook
```shell
ansible-playbook kafka.yaml -i hosts  -b
```
