## Setup dev env

1. Install python: `sudo apt install python3 python3.8-venv`
2. Create virtual env: `python3 -m venv ansible-venv`
3. Activate virtual env: `source ansible-venv/bin/activate`
4. Install dependencies: `python -m pip install -U pip wheel setuptools && pip install ansible openshift`

## Installation of new RPi

1. Setup Ubuntu OS on target RPi
2. Login via SSH and set new password: `ssh ubuntu@<ip_address>`
3. Copy your public key to target RPi: `ssh-copy-id ubuntu@<ip_address>`
4. Create inventory by duplicating "inventory_template.yml"
5. Execute provisioner: `ansible-playbook -i inventory_<name>.yml setup.yml`
