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
	$(KUBECTL) wait --for=condition=Ready $(RESOURCE_TYPE) --all --namespace $(RESOURCE_NAMESPACE)

argo_rollouts_controller_install:
	$(MAKE) -C ../01-getting-started argo_rollouts_controller_install

argo_rollouts_demo_bluegreen_install: 
	$(KUBECTL) apply -f deploy_bluegreen/rollout.yaml
	$(KUBECTL) apply -f deploy_bluegreen/service.yaml

argo_rollouts_demo_bluegreen_update: 
	$(KUBECTL) argo rollouts set image rollout-bluegreen \
	rollouts-demo=argoproj/rollouts-demo:yellow

argo_rollouts_demo_bluegreen_uninstall: 
	$(KUBECTL) delete -f deploy_bluegreen/service.yaml
	$(KUBECTL) delete -f deploy_bluegreen/rollout.yaml


argo_rollouts_demo_canary_install: 
	$(KUBECTL) apply -f deploy_canary/rollout.yaml
	$(KUBECTL) apply -f deploy_canary/service.yaml

argo_rollouts_demo_canary_update: 
	$(KUBECTL) argo rollouts set image rollouts-demo \
	rollouts-demo=argoproj/rollouts-demo:yellow

argo_rollouts_demo_canary_uninstall: 
	$(KUBECTL) delete -f deploy_canary/ingress.yaml
	$(KUBECTL) delete -f deploy_canary/service.yaml

argo_rollouts_istio_install: 
	$(KUBECTL) apply -f deploy_canary/istio.yaml

argo_rollouts_istio_uninstall: 
	$(KUBECTL) delete -f deploy_canary/istio.yaml

clean_up:
	$(MAKE) -C ../02-minikube-and-requirements clean_up
