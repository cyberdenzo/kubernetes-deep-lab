# Environment

## Участник

| Поле | Значение |
|---|---|
| Имя |  |
| GitHub |  |
| Часовой пояс |  |
| Сколько часов в неделю готов уделять |  |

## Платформа

| Поле | Значение |
|---|---|
| Тип стенда | local / selfhosted / cloud / other |
| Гипервизор | KVM / Proxmox / VMware / VirtualBox / UTM / other |
| Где расположен стенд | home lab / cloud / work lab / other |
| Есть ли возможность пересоздавать VM | yes / no |

## VM layout

| Node | Role | CPU | RAM | Disk | OS | Hostname | IP |
|---|---|---:|---:|---:|---|---|---|
| control-plane-1 | control-plane |  |  |  |  |  |  |
| worker-1 | worker |  |  |  |  |  |  |
| worker-2 | worker |  |  |  |  |  |  |

## Network

| Check | Result |
|---|---|
| Все VM видят друг друга по сети | yes / no |
| Есть SSH-доступ ко всем VM | yes / no |
| Есть интернет с каждой VM | yes / no |
| IP статические или DHCP reservation | static / dhcp-reservation / dynamic |

## Current state

Опишите текущее состояние стенда:

- VM уже созданы или будут созданы позже?
- Есть ли уже установленный Kubernetes?
- Готовы ли снести текущий кластер и начать с чистых VM?
- Есть ли ограничения по ресурсам?

## Команды проверки

Выполните на каждой VM и вставьте вывод.

### hostnamectl

    вставьте вывод здесь

### ip -br addr

    вставьте вывод здесь

### free -h

    вставьте вывод здесь

### df -h /

    вставьте вывод здесь

### nproc

    вставьте вывод здесь

## Вопросы и риски

Опишите вопросы или риски по стенду, если они есть.
