# Coinbase Market Data Collector
Provisions the infrastructure in AWS for collecting marketdata emitted by coinbase.

## Getting Started

1. Define a Virtual Environment
		```bash
		$ python3 -m venv .venv
		$ source .venv/bin/activate
		```

2. Install Pip Dependencies
	```bash
	$ pip install --upgrade pip
	$ pip install -r requirements.txt
	```

3. Install Ansible-Galaxy Dependencies
	```bash
	$ ansible-galaxy install -r ansible-galaxy.txt
	```


## Provisioning
```bash
$ ansible-playbook playbook.yml --vault-password-file <vault-pass> --private-key <ec2key>
```

## Clean Up
```bash
$ ansible-playbook teardown.yml --vault-password-file <vault-pass> 
```

## Generating Self-Signed Certs
See [here](https://docs.cloudera.com/HDPDocuments/Ambari-2.7.5.0/using-ambari-core-services/content/amb_set_up_https_for_grafana.html)

```bash
$ openssl genrsa -out ams-grafana.key 2048
$ openssl req -new -key ams-grafana.key -out ams-grafana.csr
$ openssl x509 -req -days 365 -in ams-grafana.csr -signkey ams-grafana.key -out ams-grafana.crt
```