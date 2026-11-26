# Домашнее задание к занятию «Хранение в K8s»



## Задание 1. Volume: обмен данными между контейнерами в поде

### Манифест
- [containers-data-exchange.yaml](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/containers-data-exchange.yaml)



### Скриншоты

**Описание пода:**

![describe-1](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/Screenshot%202026-11-26%20181725.png?raw=true)

![describe-2](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/Screenshot%202026-11-26%20181742.png?raw=true)

**Логи reader:**

![logs-1](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/Screenshot%202026-11-26%20181747.png?raw=true)

---

## Задание 2. PV и PVC

### Манифест
- [pv-pvc.yaml](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/pv-pvc.yaml)


### Скриншоты и пояснения

**PV и PVC в статусе Bound, под Running:**

![pv-bound](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/Screenshot%202026-11-26%20182436.png?raw=true)

**После удаления Deployment и PVC — PV в статусе Released:**

![pv-released](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/Screenshot%202026-11-26%20182552.png?raw=true)

Пояснение: политика `Retain` не удаляет PV автоматически при удалении PVC. PV переходит в статус `Released`.

**Файл на ноде до удаления PV:**

![file-before](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/Screenshot%202026-11-26%20182636.png?raw=true)

**Файл на ноде после удаления PV:**

![file-after](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/Screenshot%202026-11-26%20182811.png?raw=true)

Пояснение: при использовании `hostPath` + политика `Retain` удаление PV не удаляет данные с диска ноды. Файл остаётся, пока его не удалят вручную на самой ноде.

---

## Задание 3. StorageClass

### Манифест
- [sc.yaml](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/sc.yaml)



### Скриншоты

**Логи reader:**

![logs-sc](https://github.com/ryltsevavikyla-coder/kubernetes_3/blob/main/Screenshot%202026-11-26%20183040.png?raw=true)
