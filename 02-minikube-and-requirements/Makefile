PWD:=$(shell pwd)
KUBECTL:=$(shell which kubectl)
HELM:=$(shell which helm)
CODE:=$(shell which code)
MINIKUBE:=$(shell which minikube)

print_mk_env: 
	echo $(YQ)
	echo $(KUBECTL)
	echo $(HELM)
	echo $(CODE)
	echo $(MINIKUBE)

minikube_start:
	$(MINIKUBE) start

minikube_stop:
	$(MINIKUBE) stop

minikube_delete:
	$(MINIKUBE) delete

clean_up: minikube_stop minikube_delete
