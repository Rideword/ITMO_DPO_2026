# Модуль 2. Программно-инфраструктурный слой ML-систем

## Описание модуля

Модуль посвящен программно-инфраструктурным средствам ML-систем: Linux, Docker, Kubernetes, CI/CD, управление GPU-ресурсами, мониторинг и логирование.

## Тематический план

| № | Тема | Форма | Объем, ч. | Компетенция | Индикатор | Уровень |
|---|---|---|---|---|---|---|
| 2.1 | Linux для ML-инженера: cgroups, NUMA, CUDA-драйверы, htop/iotop/perf | Лекция | 2 | LC-5 | LC-5.1 | Базовый |
| 2.2 | Контейнеризация: Docker, multi-stage build, nvidia-container-toolkit | Лекция | 2 | LC-5 | LC-5.1 | Базовый |
| 2.3 | Оркестрация (Kubernetes): GPU scheduling, GPU Operator, Kubeflow, Helm | Лекция | 2 | LC-5 | LC-5.1 | Базовый |
| 2.4 | CI/CD и мониторинг: GitOps, Prometheus, Grafana, SLO | Лекция | 2 | LC-5 | LC-5.1 | Базовый |
| ПР3 | Настройка ML-окружения: CUDA, nvidia-container-toolkit, верификация | Практика | 4 | LC-5 | LC-5.1 | Базовый |
| ПР4 | Docker для ML: multi-stage образ, Docker Compose (модель+API+мониторинг) | Практика | 4 | LC-5 | LC-5.1 | Базовый |

## Содержание тем

### 2.1 Linux для ML-инженера

Linux как базовая ОС ML-платформы: процессы и ресурсы, cgroups, NUMA, драйверный стек NVIDIA/CUDA. Средства наблюдения и диагностики: nvidia-smi, htop, iotop, perf; основы безопасной работы с GPU-сервером.

### 2.2 Контейнеризация

Контейнеризация ML-приложений: устройство Docker-образа, слои и multi-stage build. Dockerfile для PyTorch/CUDA, управление зависимостями, NVIDIA Container Toolkit, воспроизводимость окружения и безопасное хранение секретов.

### 2.3 Оркестрация (Kubernetes)

Основные сущности Kubernetes и размещение GPU-нагрузок: pod, deployment, service, resource requests/limits. GPU Operator, device plugin, Helm; введение в Kubeflow и организация вычислительных пайплайнов.

### 2.4 CI/CD и мониторинг

Практики CI/CD и GitOps для ML-систем. Сбор метрик, логирование и трассировка. Prometheus, Grafana, ключевые SLI/SLO для инференса: availability, latency, error rate, GPU utilization; основы алертинга.

## Практические работы

### ПР3. Настройка ML-окружения

**Цель:** Развёртывание и проверка ML-окружения на Linux: установка и проверка драйвера NVIDIA, CUDA и cuDNN; подключение NVIDIA Container Toolkit; запуск контейнера PyTorch и верификация доступности GPU.

### ПР4. Docker для ML

**Цель:** Создание multi-stage Docker-образа для ML-сервиса. Подготовка Docker Compose-конфигурации для модели, REST/gRPC API и мониторинга; проверка воспроизводимости сборки и запуска.

## Контрольные мероприятия

| № | Вид | Название | Макс. баллы |
|---|---|---|---|
| КТ 3 | Тест | Тест по Модулю 2 (инфраструктура, CI/CD) | 25 |
| КТ 4 | Отчёт | Отчёт по ПР 3–4 (ML-окружение, Docker) | 20 |

## Нормативно-методическая связь

Материалы модуля связаны со следующими международными стандартами:

- **ISO/IEC 5338** — процессы жизненного цикла AI/ML-систем: от подготовки данных до развёртывания и обновления.
- **ISO/IEC 5259** — управление качеством данных: версионирование, документирование происхождения и ограничений.
- **ISO/IEC 42001** — роли, документирование, управление изменениями в контексте Docker, CI/CD, MLOps.
- **ISO/IEC 25059** — эксплуатационные характеристики AI-сервиса: надёжность, масштабируемость, управляемость.

Подробная карта стандартов и учебных артефактов: [resources/ai-standards/README.md](../resources/ai-standards/README.md).

## Ресурсы

- Docker documentation
- NVIDIA Container Toolkit documentation
- Kubernetes GPU Operator documentation
- Kubeflow documentation
- ArgoCD documentation
- Prometheus + Grafana documentation
- man-pages; Ubuntu Server Guide

## Структура модуля

| Файл | Описание |
|---|---|
| [Конспект лекций](Modul-2_Lectures_Konspekt.md) | Подробный конспект по темам 2.1–2.4 |
| [Вопросы к лекциям](Module-2_Lectures_Questions.md) | Вопросы для самопроверки по темам модуля |
| [Руководство по практическим работам](Module-2_Practice_Guide.md) | Инструкции по выполнению ПР3 и ПР4 |
| [Критерии оценки практических работ](Module-2_Practice_Grading.md) | Рубрики и критерии оценивания ПР3 и ПР4 |
| [Ресурсы: ПО и оборудование](Module-2_Resources_Software-Hardware.md) | Список программного обеспечения и аппаратных ресурсов |
| [Руководство для преподавателя](Module-2_Teacher_Lectures_Guide.md) | Методические указания для преподавателя |
| [Тест по модулю](Module-2_Test.md) | Тестовые вопросы для контроля знаний |
| [Приложения](attachments/) | Дополнительные материалы к модулю |

