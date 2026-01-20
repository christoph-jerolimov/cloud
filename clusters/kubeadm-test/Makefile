export ANSIBLE_INVENTORY=inventory.yaml
export ANSIBLE_PYTHON_INTERPRETER=auto_silent

run:
	ansible-playbook playbook.yaml

install-dependencies:
	ansible-galaxy collection install git+https://github.com/k3s-io/k3s-ansible.git

cleanup:
	ansible-playbook cleanup.yaml

check:
	ansible-playbook --check playbook.yaml cleanup.yaml

ssh:
	hcloud server ssh k8s-test

open:
	gnome-open http://$(shell hcloud server ip k8s-test)
