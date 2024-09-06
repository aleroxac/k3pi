# k3pi
Utility to automate terraforming a fully out-of-the-box k3s cluster using Raspberry Pi as cluster nodes.



## Goal
### Base Cluster Setup
- Setup a k3s cluster using 3 raspberry pi boards, with 1 control-plane node and 2 worker nodes
- Setup metal-lb as service-lb
- Setup longhorn as storage-provider

### Setup Method
- Automate the entire setup



## Requirements
- 3x Raspberry Pi 4 boards with 2GB of memory, 4 CPU cores
- 3x SD Card with 16GB
- 3x power supply 5V/3A with USB type-c conector
- 3x ethernet patch cord CAT5-e
- 1x Internet Modem or Switch with least 3x 10/100 Mbps ports available and least 1 uplink port



## Usemode
``` shell
### Create cluster
git clone github.com/aleroxac/k3pi && cd k3pi
make init
make apply

### Cleanup
make destroy
```



## TO-DOs(core)
``` yaml
init:
    - build-image:
        description: "Build container image to be used by all automations"
        tasks:
            - [ ] install python3, python3-pip, poetry
            - [ ] install blue, black, isort, autopep8 darker, yapf 
            - [ ] install flake8, pylint, pydocstyle, bandit, radon, prospector, pypy
            - [ ] install pytest, tox, python-precommit
            - [ ] install ansible, molecule, mitogen, testinfra, yamllint
            - [ ] setup python
            - [ ] setup ansible
            - [ ] setup molecule
            - [ ] setup mitogen

validate:
    - check-raspi:
        description: "Check SSH connectivy with raspberry pi servers"
        tasks: 
            - [ ] ssh-access

plan:
    - cluster-nodes:
    - cluster-groundwork:
    - cluster-utils:

apply:
    - setup-master:
    - setup-worker:

destroy:
    - reset-cluster:
    - cleanup-k3s-files:
    - cleanup-k3s-folders:
    - cleanup-firewall-rules:
    - cleanup-local-files:
    - cleanup-local-folders:
```



## Backlog tasks
``` yaml
ansible / testinfra / molecule / mitogen
terraform / testinfra + terratest / terragrunt / atlantis / im2nguyen/rover / terraform-docs / localstack/tflocal
packer / vagrant

rapido
testavel
modular
customizavel
confiavel
seguro
facil
leve
complexo
```



## Backlog plus tasks
``` yaml
- manage:
    - upgrade
    - downgrade
    - backup
    - restore

- scan:
    - cluster
    - image
    - files

- autodestroy

- clean
- autoclean
```



## Backlog extra tasks
``` yaml
- test: 
    - unit
    - integ
    - load
    - e2e
    - chaos

- export
- import

- explain
- inspect
- describe
- graph
- get

- example:
    - pod/deploy/statefulset/daemonset
    - job/cronjob
    - service/ingress

- demo:
    - guided
    - explorer
    - dryrun

- set: 
    - defcon 1-5
    - log true/false
    - log-level 1-10
    - log-path
    - log-name
    - log-format
```




## Overkill tasks
- migrate from raspi-os to diet-pi
- migrate from flannel to calico as cni-plugin
- migrate from sqlite to etcd as datastore
- migrate from metrics-server to prometheus-adapter
- set parameter configs via config file instead command line flags

- enable k3s secrets encryption
- certificate rotation
- rootless-mode
- enable SElinux
- enable Lazy Pulling of eStargz
- add additional network policy logging

- backup/restore logs
- backup/restore datastore

- upgrade cluster
- downgrade cluster

- set net-booting
- set airgap-install

- private-registry: harbor
- artifact-manager: nexus
- secret-manager: vault
- certificate-manager: cert-manager
- ingress-controller: nginx / traefik / kong
- api-gateway: kong
- auth/authz: authentik / keycloak
- service-mesh: istio
- service-discovery: consul

- ci-platform: github-action-runner / gitlab-action-runner
- cd-platform: argocd / fluxcd



## References
- reference-01
- reference-02
- reference-03
- reference-04
- reference-05
