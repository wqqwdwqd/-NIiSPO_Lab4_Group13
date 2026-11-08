# Лабораторная работа №4

## Методы и средства оркестрации в многоконтейнерных системах

**Дисциплина:** Непрерывное интегрирование и сборка программного обеспечения  
**Студент:** Han Yu  
**Группа:** 13  
**Преподаватель:** Давидовская М. И.

## Описание

В данной лабораторной работе изучаются основные принципы оркестрации контейнеров с помощью Kubernetes.

В соответствии с требованиями для группы 13 выполнены задания №1 и №2:

1. Подготовка окружения и создание локального Kubernetes-кластера.
2. Изучение ресурсов Kubernetes, Pod, постоянных томов и ReplicaSet.

## Используемые технологии

- Windows
- Docker Desktop
- Kubernetes
- kubectl
- kind
- YAML
- Git и GitHub

## Результаты

- Создан локальный кластер `lab4-group13`.
- Узел Kubernetes находится в состоянии `Ready`.
- Изучены системные Pod и пространства имён.
- Создан PVC `lab4-pvc` объёмом 1Gi, получен статус `Bound`.
- Создан ReplicaSet `lab4-replicaset` с тремя работающими Pod.
- Выполнено масштабирование ReplicaSet с 3 до 5 реплик.

## Исходные файлы

- [storage-demo.yaml](storage-demo.yaml) — создание PVC и Pod с подключённым томом.
- [replicaset-demo.yaml](replicaset-demo.yaml) — создание ReplicaSet.

## Отчёт

**[Открыть отчёт по лабораторной работе №4](docs/lab4_report.md)**

Отчёт содержит цель работы, описание заданий, YAML-конфигурации, результаты проверок и ответы на 23 контрольных вопроса.

## Основные команды

```bash
kind create cluster --name lab4-group13
kubectl get nodes
kubectl get pods -A
kubectl get namespaces
kubectl get storageclass
kubectl apply -f storage-demo.yaml
kubectl get pods,pvc,pv
kubectl apply -f replicaset-demo.yaml
kubectl get rs
kubectl get pods -l app=lab4-rs-demo
kubectl scale rs lab4-replicaset --replicas=5
```

## Автор

Han Yu, группа 13, БГУ, Минск, 2026.