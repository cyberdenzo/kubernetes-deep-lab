# Требования к участникам и стенду

Этот документ описывает требования для участия в Kubernetes Deep Lab: Cohort 1.

## Цель

Цель проекта - изучать Kubernetes глубоко через VM-based lab.

Участники будут работать с:

- Linux
- containerd
- kubeadm
- Kubernetes control plane
- kubelet
- CNI
- Services
- DNS
- storage
- RBAC
- troubleshooting
- upgrades
- failure scenarios

## Требования к участнику

Участнику желательно иметь:

- базовые навыки Linux shell
- базовые навыки Git и GitHub
- возможность создать минимум 2 VM
- возможность подключаться к VM по SSH
- готовность уделять 4-6 часов в неделю
- готовность вести lab journal
- готовность присылать выводы команд и troubleshooting notes

## Минимальный стенд

| Node | CPU | RAM | Disk |
|---|---:|---:|---:|
| control-plane-1 | 2 vCPU | 4 GB | 30 GB |
| worker-1 | 2 vCPU | 4 GB | 40 GB |

Итого минимум:

| Resource | Value |
|---|---:|
| CPU | 4 vCPU |
| RAM | 8 GB |
| Disk | 70 GB |

## Рекомендуемый стенд

| Node | CPU | RAM | Disk |
|---|---:|---:|---:|
| control-plane-1 | 2 vCPU | 4 GB | 30 GB |
| worker-1 | 2 vCPU | 4 GB | 40 GB |
| worker-2 | 2 vCPU | 4 GB | 40 GB |

Итого рекомендуется:

| Resource | Value |
|---|---:|
| CPU | 6 vCPU |
| RAM | 12 GB |
| Disk | 110 GB |

## Поддерживаемые платформы

Рекомендуется:

- KVM/libvirt
- Proxmox
- self-hosted server

Также допустимо:

- VMware
- VirtualBox
- UTM
- cloud VMs

## Операционная система

Основная ОС для первой когорты:

    Ubuntu 24.04 LTS

Другие Linux-дистрибутивы могут работать, но начальная документация будет ориентирована на Ubuntu 24.04 LTS.

## Базовый стек Kubernetes

| Component | Choice |
|---|---|
| Runtime | containerd |
| Bootstrap tool | kubeadm |
| First CNI | Calico |
| Later CNI deep dive | Cilium |
| Main access method | SSH |

## Сетевые требования

Каждая VM должна иметь:

- стабильный IP address
- корректный hostname
- SSH access
- internet access
- сетевую доступность до остальных lab VM

Пример hostnames:

    control-plane-1
    worker-1
    worker-2

## Что не нужно делать до первой лабораторной

Не устанавливайте заранее:

- Kubernetes
- kubeadm
- kubelet
- kubectl
- CNI plugin
- Helm
- Argo CD
- готовый Kubernetes-дистрибутив

Первый шаг - environment validation. Нам нужны чистые VM или возможность быстро пересоздать чистые VM.

## Zero Task

Перед принятием в когорту кандидат выполняет Zero Task:

1. Делает fork репозитория.
2. Создает `students/<github-username>/environment.md`.
3. Описывает свой lab environment.
4. Открывает Pull Request.

## Критерии готовности

Кандидат готов к участию, если может предоставить:

- GitHub username
- список VM
- CPU/RAM/Disk по каждой VM
- OS version
- hostnames
- IP addresses
- подтверждение SSH access
- подтверждение internet access
- подтверждение network connectivity между VM
- подтверждение, что VM можно пересоздать или очистить
