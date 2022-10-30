This repo is created to have all ansible playbooks.

Note - not related to ansible. I have used this same repo to keep some linux kernel building things. Go to
```ignore/linux``` for more details.

## Setup Kafka
Setup can be fond in ```kafka_playbook``` dir
```shell
ansible-playbook kafka.yaml -i hosts  -b
```

---
# Miscellaneous

### Check the status and type of ZK on a spefific node
You can check if ZK is running as leader or follower

```shell
# Location of ZK bin = 
cd /usr/share/apache-zookeeper-3.7.1/bin/

# Check if this is a follower or a master
sudo ./zkServer.sh status

>> This will print "follower" or "leader"
```
---

### Setup VMs using multipass
1. Setup VMs
```shell
multipass launch --name ans1
multipass launch --name ans2
multipass launch --name ans3
```
2. Make sure you add your SSH to work 
```ssh
cat ~/.ssh/id_rsa.pub  | multipass exec ans1 -- tee -a .ssh/authorized_keys
cat ~/.ssh/id_rsa.pub  | multipass exec ans2 -- tee -a .ssh/authorized_keys
cat ~/.ssh/id_rsa.pub  | multipass exec ans3 -- tee -a .ssh/authorized_keys
```
3. SSH once to each node
```shell
# Change your IPs
ssh ubuntu@192.168.64.41
ssh ubuntu@192.168.64.42
ssh ubuntu@192.168.64.43
```
