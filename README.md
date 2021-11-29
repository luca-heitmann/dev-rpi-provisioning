## Setup dev env

1. Install python and dependencies:

```
sudo apt install python3 python3.8-venv
python3 -m venv ansible-venv
source ansible-venv/bin/activate
python -m pip install -U pip wheel setuptools && pip install ansible openshift
```

2. Install kubectl:

```
sudo apt-get update && sudo apt-get install -y apt-transport-https
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl
```

3. Install helm:

```
curl https://baltocdn.com/helm/signing.asc | sudo apt-key add -
sudo apt-get install apt-transport-https --yes
echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
sudo apt-get update
sudo apt-get install helm
```

## Installation of new RPi

1. Setup Ubuntu OS on target RPi
2. Login via SSH and set new password: `ssh ubuntu@<ip_address>`
3. Copy your public key to target RPi: `ssh-copy-id ubuntu@<ip_address>`
4. Create inventory by duplicating "inventory_template.yml"
5. Execute provisioner: `ansible-playbook -i inventory_<name>.yml setup_<k3s | docker>.yml`
