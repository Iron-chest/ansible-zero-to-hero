# Setup EC2 Collection and Authentication

## Install Python3

```
sudo apt install python3-pip -y
```

## Install boto3

```
pip install boto3
```

## Install AWS Collection

```
ansible-galaxy collection install amazon.aws
```

## Setup Vault 

1. Create a password for vault

```
openssl rand -base64 2048 > vault.pass
```

2. Add your AWS credentials using the below vault command

```
ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass
```
3. To create AWS resources using ansible galaxy while using the created vault password
```
ansible-playbook <playbook-yaml-file> --vault-password-file vault.pass
```




