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
	hcloud server ssh argocd3-test

open:
	gnome-open http://$(shell hcloud server ip argocd3-test)

get-kubeconfig:
	@hcloud server ssh argocd3-test -- cat /etc/kubernetes/admin.conf \
		| sed 's/127.0.0.1:6443/$(shell hcloud server ip argocd3-test):6443/g' \
		> kubeconfig.yaml
	@echo
	@echo "Please run export KUBECONFIG=\$$(pwd)/kubeconfig.yaml"
	@echo
	@echo "You can then run: kubectl get nodes"
	@echo

argocd-get-admin-password:
	kubectl -n argocd get secrets/argocd-initial-admin-secret -o jsonpath='{.data.password}' | base64 -d
	@echo

argocd-port-forward:
	kubectl port-forward svc/argocd-server -n argocd 8080:443
