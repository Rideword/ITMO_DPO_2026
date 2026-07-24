**Дисциплина:** **«Аппаратно-программные платформы для систем ИИ».**

**Модуль 2\. Программно-инфраструктурный слой: Linux, контейнеры, оркестрация, CI/CD, мониторинг**

**Методические указания к практическим работам**

**Практические занятия**

**2.1. ML-окружение**

**1\. Цель**.

Продемонстрировать навыки создания и эксплуатации контейнеров для ML.

**2\. Формируемые компетенции** 

* LC-5 —Способен применять и (или) проектировать различные инструменты и инженерные практики промышленной разработки, развертывания, эксплуатации и мониторинга систем ИИ.

* LC-5.1. Осуществляет выбор инструментов и инженерных практик промышленной разработки систем ИИ, развертывания и сопровождения моделей МО в продуктивной среде

* Уровень сформированности индикатора компетенции.

* Умеет устанавливать CUDA;

* Способен запускать PyTorch в контейнере;

* Умеет верифицировать доступность GPU.

**3\. Задание (последовательность действий:**

1\. 	Написать Dockerfile для образа с PyTorch (или TensorFlow) и базовым набором зависимостей (numpy, pandas, scikit-learn)

2\.	Использовать multistage build для уменьшения размера финального образа.

3\.	Настроить volume для хранения данных/моделей.

4\. 	Запустить контейнер с доступом к GPU, выполнить скрипт тренировки небольшой модели и зафиксировать логи.

5\.	Закоммитить Dockerfile, docker-compose (опционально) и скрипт тренировки в репозиторий, написать краткий README с инструкциями.

**4\. Критерии оценки (макс. 100 баллов):**

работоспособность Dockerfile (40)

корректность использования volumes и сетей (30)

использование best practices (multistage build, непривилегированный пользователь) (20)

краткий отчёт с инструкциями (10)

**Общие требования к отчету:**

* Структура: титульный лист, введение, анализ задачи, структура Dockerfile, ограничения конкретного GPU применительно к объему модели, заключение, список источников.

* Объем: 10–15 страниц, шрифт Times New Roman 14, полуторный интервал.


**5\. Ссылки**: 

Официальная документация:

Ubuntu Server Guide — [https://ubuntu.com/server/docs](https://ubuntu.com/server/docs)

Docker Documentation — [https://docs.docker.com](https://docs.docker.com)

NVIDIA CUDA Toolkit Documentation — [https://docs.nvidia.com/cuda](https://docs.nvidia.com/cuda)

NVIDIA Container Toolkit — [https://docs.nvidia.com/datacenter/cloud-native/container-toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit)

Книги и руководства:

"Linux for Developers" — авторов/изданий по выбору (руководство по практическому использованию Linux).

"Docker Deep Dive" — Nigel Poulton (для понимания контейнеров).

Статьи и учебные материалы по ML ops:

“Best Practices for GPU Cluster Management” — статьи от NVIDIA Developer Blog.

Практические руководства и примеры:

GitHub: официальные Docker образы PyTorch / TensorFlow (пакеты с CUDA): [https://hub.docker.com/r/pytorch/pytorch](https://hub.docker.com/r/pytorch/pytorch), [https://hub.docker.com/r/tensorflow/tensorflow](https://hub.docker.com/r/tensorflow/tensorflow)

Руководства по установке драйверов NVIDIA на Ubuntu (официальные и community HOWTO).

| CUDA Programming Guide v12 | [https://docs.nvidia.com/cuda/cuda-c-programming-guide/](https://docs.nvidia.com/cuda/cuda-c-programming-guide/)  |
| :---- | :---- |
| CUDA Toolkit Documentation v12.0 | [https://docs.nvidia.com/cuda/](https://docs.nvidia.com/cuda/)  |
| NVIDIA GPU Architecture Whitepapers | [https://www.nvidia.com/en-us/geforce/news/](https://www.nvidia.com/en-us/geforce/news/) |
| PyTorch Profiler Documentation | [https://docs.pytorch.org/](https://docs.pytorch.org/)  |
| NVIDIA DCGM Documentation | [https://docs.nvidia.com/dcgm/](https://docs.nvidia.com/dcgm/)  |
| NVIDIA DCGM Product Page | [https://developer.nvidia.com/dcgm](https://developer.nvidia.com/dcgm)  |
| NVIDIA Developer Blog | [https://developer.nvidia.com/blog/](https://developer.nvidia.com/blog/) |

**6\. Материалы для раздачи студентам (шаблоны)**

Пример Dockerfile (с комментариями). 

Может быть сформирован преподавателем на основе материалов, предоставленных индустриальным партнером ВУЗа

Пример docker-compose.yml для локального развёртывания.

Чек-лист best practices по безопасности и оптимизации образов.

Шаблон README для репозитория.

**Практические занятия**

**2.2. Docker для ML**

**1\. Цель**.

Продемонстрировать навыки настройки CI/CD и мониторинга для ML‑систем.

**2\. Формируемые компетенции** 

* LC-5 —Способен применять и (или) проектировать различные инструменты и инженерные практики промышленной разработки, развертывания, эксплуатации и мониторинга систем ИИ.

* LC-5.1. Осуществляет выбор инструментов и инженерных практик промышленной разработки систем ИИ, развертывания и сопровождения моделей МО в продуктивной среде

* Уровень сформированности индикатора компетенции.

* Умеет собирать оптимизированный ML-образ.

* Способен запускать Docker Compose с сервисом инференса.

* Способен осуществлять мониторинг систем ИИ.

**3\. Задание (последовательность действий:**

1\. 	Настроить CI-пайплайн (GitHub Actions/GitLab CI) для ML-проекта:

этап тестирования кода (pytest),

этап сборки Docker-образа,

этап пуша образа в реестр.

(Опционально) настроить CD: автоматическое развёртывание в Kubernetes/локально.

2\.	Настроить Prometheus для сбора метрик приложения (или использовать готовый exporter).

3\.	Создать дашборд в Grafana для визуализации метрик (задержка, ошибки, загрузка CPU/GPU).

4	Настроить сбор логов (Loki/ELK) и поиск по логам.

5\.	Закоммитить конфигурации (workflow, Dockerfile, Prometheus/Grafana конфиги) в репозиторий, написать краткий README.

**4\. Критерии оценки (макс. 100 баллов):**

работоспособность пайплайна (40),

корректность настройки мониторинга (30),

наличие дашборда и алертов (20),

краткий отчёт с инструкциями (10).

**Общие требования к отчету:**

* Структура: титульный лист, введение, анализ задачи, описание этапов настройки CI-пайплайна, выбор и обоснование метрик и собираемых логов, заключение, список источников.

* Объем: 10–15 страниц, шрифт Times New Roman 14, полуторный интервал.

**5\. Ссылки:**

Официальная документация:

GitHub Actions Documentation — https://docs.github.com/actions

GitLab CI/CD Documentation — https://docs.gitlab.com/ee/ci

Jenkins Documentation — https://www.jenkins.io/doc

Argo CD Documentation — https://argo-cd.readthedocs.io

Prometheus Documentation — https://prometheus.io/docs

Grafana Documentation — https://grafana.com/docs

Elasticsearch Documentation — https://www.elastic.co/guide

Loki Documentation — https://grafana.com/docs/loki

OpenTelemetry Documentation — https://opentelemetry.io/docs

Jaeger Documentation — https://www.jaegertracing.io/docs

Книги и руководства:

“Continuous Delivery” — Jez Humble, David Farley (классика CI/CD).

“Site Reliability Engineering” — Google SRE Team (надёжность, мониторинг, SLO).

“Kubernetes in Action” — Marko Lukša (раздел про мониторинг и CI/CD).

Материалы по ML Ops:

MLflow Documentation — https://mlflow.org/docs

DVC Documentation — https://dvc.org/doc

“Machine Learning Engineering” — Andriy Burkov (разделы про CI/CD для ML).

Практические ресурсы:

DCGM‑exporter (GPU метрики) — https://github.com/NVIDIA/dcgm-exporter

Примеры workflow GitHub Actions для ML — https://github.com/marketplace?type=actions\&query=ml

Готовые дашборды Grafana для Kubernetes и ML — https://grafana.com/grafana/dashboards

**6\. Материалы для раздачи студентам (шаблоны)**

Пример workflow GitHub Actions / .gitlab-ci.yml для ML‑проекта.

Пример Dockerfile для ML‑сервиса.

Может быть сформирован преподавателем на основе материалов, предоставленных индустриальным партнером ВУЗа

Пример конфигурации Prometheus (scrape config) и дашборда Grafana (JSON).

Чек‑лист best practices по CI/CD и мониторингу.

Шаблон README для репозитория.