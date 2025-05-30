export ANSIBLE_INVENTORY=inventory.yaml
export ANSIBLE_PYTHON_INTERPRETER=auto_silent

check:
	ansible-playbook --check playbook.yaml

update:
	ansible-playbook --ask-become-pass playbook.yaml
