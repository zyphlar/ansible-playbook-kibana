ansible-playbook-kibana
=======================

This repo is a set of playbooks which will deploy Logstash + ElasticSearch + Kibana all on a single server.

### Setup

To get started you will need to setup `./vars/global_vars.yml`. To do this I recommend just copying `./vars/global_vars.yml.sample` and filling in the variables to whatever you want.

```shell
cp ./vars/global_vars.yml.sample ./vars/global_vars.yml
vi ./vars/global_vars.yml
```

You'll also need to setup ansible's inventory to define the `central-logging` host.

```shell
sudo vi /etc/ansible/hosts
```
and add

```ini
[central-logging]
foo.com
```

Finally, unless your user account name is ubuntu with sudo access, you'll need to edit each playbook to change the username.
```shell
vi ./playbooks/*
```


### Running Ansible

There are a few ways to use this set of playbooks -- you can either run the deployment of each service individually, or you can run them all in one go.



##### All Services

```shell
ansible-playbook playbooks/all.yml
```


##### Just ElasticSearch

```shell
ansible-playbook playbooks/elasticsearch.yml
```

##### Just LogStash

```shell
ansible-playbook playbooks/logstash.yml
```

##### Just Kibana3

```shell
ansible-playbook playbooks/kibana.yml
```

