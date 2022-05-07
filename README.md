# Monitoring
Monitoring example based on Vagrant - virtual machine environment, defined in code.

## Running the example 

* Clone the repository and run `vagrant up` - this will setup the vagrant machine with prometheus/grafana monitoring and ELK stack for logging.

Following services are available:

 * Prometheus: 192.168.44.44:9090
 * Grafana:  192.168.44.44:3000 (login - admin:panda)
 * Alertmanager: 192.168.44.44:9093
 * Cadvisor: 192.168.44.44:8080
 * Node exporter 192.168.44.44:9100
 * Blackbox exporter: 192.168.44.44:9115
-----------
 * Elasticsearch: 192.168.44.44:9200
 * Logstash:  192.168.44.44:4560 
 * Kibana: 192.168.44.44:5601
