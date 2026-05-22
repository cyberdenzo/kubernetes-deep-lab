# Roadmap

Этот документ описывает учебный путь Kubernetes Deep Lab.

Цель - пройти путь от Linux и container runtime до production-like Kubernetes operations.

## Принципы

- Сначала ручное понимание, потом автоматизация.
- Сначала проверяем состояние, потом меняем.
- Основной стенд - VM-based lab.
- Основной источник истины - официальная документация и фактический вывод команд.
- Не перескакиваем к Helm, GitOps и service mesh до понимания базовых слоев.
- Документируем команды, выводы, ошибки и исправления.

## Phase 0 - Environment and workflow

Цель: подготовить lab environment и GitHub workflow.

Темы:

- GitHub workflow
- lab journal
- VM requirements
- SSH access
- hostnames and IPs
- environment validation

Labs:

- lab-00-environment

## Phase 1 - Linux and container runtime baseline

Цель: понять Linux-слой под Kubernetes.

Темы:

- processes
- systemd basics
- namespaces
- cgroups
- networking basics
- container images
- OCI runtime
- runc
- containerd
- CRI
- crictl

Labs:

- Linux baseline checks
- containerd installation
- container runtime inspection
- running containers without Kubernetes

## Phase 2 - kubeadm cluster bootstrap

Цель: собрать первый Kubernetes cluster через kubeadm.

Темы:

- kubeadm
- kubelet
- kubectl
- Kubernetes packages
- static Pods
- bootstrap tokens
- node join
- cluster initialization
- CNI installation

Labs:

- prepare nodes
- install containerd
- install kubeadm, kubelet, kubectl
- initialize control plane
- join worker nodes
- install first CNI
- verify cluster health

## Phase 3 - Control plane internals

Цель: понять, что создал kubeadm и как работает control plane.

Темы:

- API Server
- etcd
- Controller Manager
- Scheduler
- static Pod manifests
- certificates
- kubeconfig files
- readiness and health checks

Labs:

- inspect /etc/kubernetes
- inspect static Pods
- inspect certificates
- inspect kubeconfigs
- query API Server health endpoints
- inspect etcd basics

## Phase 4 - Node internals and Pod lifecycle

Цель: понять, как Pod попадает на node и запускается.

Темы:

- kubelet
- container runtime
- CRI
- Pod sandbox
- pause container
- Pod lifecycle
- probes
- events
- logs
- resource requests and limits
- QoS classes
- eviction basics

Labs:

- inspect kubelet status and logs
- trace Pod creation
- debug Pending Pod
- debug CrashLoopBackOff
- inspect container runtime state

## Phase 5 - Workloads

Цель: понять Kubernetes workload controllers.

Темы:

- Pod
- ReplicaSet
- Deployment
- DaemonSet
- StatefulSet
- Job
- CronJob
- rollout
- rollback
- labels and selectors

Labs:

- create Deployment
- inspect ReplicaSet ownership
- perform rollout and rollback
- run DaemonSet
- compare Deployment and StatefulSet
- debug failed workload

## Phase 6 - Networking

Цель: глубоко понять Kubernetes networking.

Темы:

- Linux network namespaces
- veth
- bridges
- routing
- iptables/nftables
- conntrack
- Pod IP
- Service IP
- ClusterIP
- NodePort
- LoadBalancer concept
- kube-proxy
- CoreDNS
- NetworkPolicy
- CNI
- Calico
- Cilium later

Labs:

- trace Pod-to-Pod traffic
- inspect Service routing
- debug DNS
- inspect kube-proxy rules
- apply NetworkPolicy
- compare allowed and denied traffic

## Phase 7 - Ingress and Gateway

Цель: понять входящий трафик в cluster.

Темы:

- Ingress
- Ingress Controller
- Gateway API
- TLS basics
- cert-manager later
- external access patterns

Labs:

- deploy ingress controller
- expose test app
- configure host-based routing
- inspect traffic path

## Phase 8 - Storage

Цель: понять Kubernetes storage abstractions и CSI.

Темы:

- Volume
- PersistentVolume
- PersistentVolumeClaim
- StorageClass
- access modes
- reclaim policy
- volume binding mode
- CSI
- StatefulSet storage
- snapshots later

Labs:

- create static PV/PVC
- use dynamic provisioning
- inspect StatefulSet volumes
- test reclaim policy
- debug Pending PVC

## Phase 9 - Security

Цель: понять access control и workload security.

Темы:

- ServiceAccount
- RBAC
- Role
- ClusterRole
- RoleBinding
- ClusterRoleBinding
- admission controllers
- Pod Security Admission
- securityContext
- secrets
- image pull secrets

Labs:

- create limited ServiceAccount
- test RBAC permissions
- debug Forbidden errors
- apply Pod Security restrictions
- inspect secrets usage

## Phase 10 - Observability

Цель: научиться наблюдать и диагностировать Kubernetes.

Темы:

- events
- metrics
- logs
- kubelet logs
- control plane logs
- Prometheus
- Grafana
- Loki later
- alerting basics

Labs:

- collect cluster events
- inspect component logs
- deploy metrics-server
- deploy basic monitoring stack
- debug resource pressure

## Phase 11 - Operations and failure scenarios

Цель: отработать production-like operations.

Темы:

- cordon
- drain
- node failure
- control plane failure
- etcd backup
- etcd restore
- certificate expiration
- upgrades
- disaster recovery

Labs:

- drain a node
- simulate node failure
- backup etcd
- restore etcd in lab
- perform kubeadm upgrade
- inspect certificates

## Phase 12 - GitOps and automation

Цель: перейти от ручного понимания к контролируемой автоматизации.

Темы:

- Helm
- Kustomize
- Argo CD or Flux
- GitOps workflow
- Ansible later
- IaC later

Labs:

- package simple app with Helm
- deploy with Kustomize
- bootstrap GitOps
- automate only what was previously understood manually

## Не входит в стартовый этап

На старте не занимаемся:

- service mesh
- complex HA production design
- multi-cluster
- full cloud provider integration
- heavy automation before manual understanding
- managed Kubernetes as the main learning path

## Текущий статус

Cohort 1 готовится к запуску.

Фокус сейчас:

- собрать кандидатов
- подготовить GitHub repository
- подготовить Zero Task
- проверить lab environments
- стартовать с clean VM-based labs
