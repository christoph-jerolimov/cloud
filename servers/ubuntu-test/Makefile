export ANSIBLE_INVENTORY=inventory.yaml
export ANSIBLE_PYTHON_INTERPRETER=auto_silent

check:
	ansible-playbook --check playbook.yaml cleanup.yaml

update:
	ansible-playbook playbook.yaml

cleanup:
	ansible-playbook cleanup.yaml

ssh:
	hcloud server ssh ubuntu-test
