PWD:=$(shell pwd)
YQ:=$(shell which yq)
KUBECTL:=$(shell which kubectl)
HELM:=$(shell which helm)
CODE:=$(shell which code)
MINIKUBE:=$(shell which minikube)

print_mk_env: 
	echo $(PWD)
	echo $(YQ)
	echo $(KUBECTL)
	echo $(HELM)
	echo $(CODE)
	echo $(MINIKUBE)

wait_for_resources: 
	kubectl wait --for=condition=Ready $(RESOURCE_TYPE) --all --namespace $(RESOURCE_NAMESPACE)

init: 
	kubectl create namespace argo-rollouts

uninit: 
	kubectl delete namespace argo-rollouts

argo_rollouts_controller_install: 
	$(MAKE) -C ../02-minikube-and-requirements minikube_start
	$(MAKE) init 
	$(KUBECTL) apply -n argo-rollouts -f https://github.com/argoproj/argo-rollouts/releases/latest/download/install.yaml

argo_rollouts_controller_uninstall: init 
	$(KUBECTL) delete -n argo-rollouts -f https://github.com/argoproj/argo-rollouts/releases/latest/download/install.yaml

argo_rollouts_demo_install: 
	$(KUBECTL) apply -f https://raw.githubusercontent.com/argoproj/argo-rollouts/master/docs/getting-started/basic/rollout.yaml
	$(KUBECTL) apply -f https://raw.githubusercontent.com/argoproj/argo-rollouts/master/docs/getting-started/basic/service.yaml

argo_rollouts_demo_uninstall: 
	$(KUBECTL) delete -f https://raw.githubusercontent.com/argoproj/argo-rollouts/master/docs/getting-started/basic/rollout.yaml
	$(KUBECTL) delete -f https://raw.githubusercontent.com/argoproj/argo-rollouts/master/docs/getting-started/basic/service.yaml

clean_up:
	$(MAKE) -C ../02-minikube-and-requirements clean_up