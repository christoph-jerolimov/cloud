export ANSIBLE_INVENTORY=inventory.yaml
export ANSIBLE_PYTHON_INTERPRETER=auto_silent

run:
	ansible-playbook playbook.yaml

install-dependencies:
	ansible-galaxy install -r requirements.yml

cleanup:
	ansible-playbook cleanup.yaml

check:
	ansible-playbook --check playbook.yaml cleanup.yaml

ssh:
	hcloud server ssh argocd-test

open:
	gnome-open http://$(shell hcloud server ip argocd-test)
