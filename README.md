# 800GZRPOC
Basic Ansible playbooks to help setup mock environment for testing.
## Initial Provisioning
One playbook is used to push the initial addressing and IS-IS configs. It'll use the default inventory.
* push_initial_configuration.yml
## Test 1 800G-ZR+ Max Distance
Two playbooks are made to support this. They will use the default inventory. They configure the zr wavelength and remove it.
* zr_setup.yml
* zr_cleanup.yml
```ansible-playbook zr_setup.yml```

## Test 2 800G MACsec PTX to PTX
Two playbooks are made to support this. Use the "inventory_800gmacsec" for these playbooks.
* 800Gmacsec_setup.yml
* 800Gmacsec_cleanup.yml
```ansible-playbook 800Gmacsec_setup.yml -i inventory_800gmacsec```

## Test 3 WAN MACsec (VLAN in Clear-text) Max Sessions
Two playbooks used to support this. Max sessions is just 32 for this example. Use the inventory_wanmacsec with these playbooks.
* wanmacsec_setup.yml
* wanmacsec_cleanup.yml
```ansible-playbook wanmacsec_setup.yml -i inventory_wanmacsec```

## Install
This was tested with ansible core 2.15.12 and python 3.9.6. Install in a virtual environment.
```
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
ansible-galaxy install -r roles/requirements.yml --roles-path ./roles/
```
