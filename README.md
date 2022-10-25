This repo is created to have all ansible playbooks

## Setup Kafka
Setup can be fond in ```kafka_playbook``` dir
```shell
ansible-playbook kafka.yaml -i hosts  -b
```

---
### Miscellaneous

### Check the status and type of ZK on a spefific node
You can check if ZK is running as leader or follower

```shell
# Location of ZK bin = 
cd /usr/share/apache-zookeeper-3.7.1/bin/

# Check if this is a follower or a master
sudo ./zkServer.sh status

>> This will print "follower" or "leader"
```