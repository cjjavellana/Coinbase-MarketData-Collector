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