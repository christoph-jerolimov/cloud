export ANSIBLE_INVENTORY=inventory.yaml
export ANSIBLE_PYTHON_INTERPRETER=auto_silent

run:
	ansible-playbook playbook.yaml

cleanup:
	ansible-playbook cleanup.yaml

check:
	ansible-playbook --check playbook.yaml cleanup.yaml

ssh:
	hcloud server ssh centos-test

open:
	gnome-open http://$(shell hcloud server ip centos-test)
