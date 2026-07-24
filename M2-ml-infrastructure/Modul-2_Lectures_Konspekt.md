**Дисциплина:** **«Аппаратно-программные платформы для систем ИИ».**

**Модуль 2\. Программно-инфраструктурный слой: Linux, контейнеры, оркестрация, CI/CD, мониторинг**

**ОПОРНЫЙ КОНСПЕКТ ЛЕКЦИЙ**

**Лекция 2.1. Linux для ML**

**1\. Цель лекции**  
Обеспечить у студентов практическое и концептуальное понимание использования Linux как базовой операционной системы для разработки, развертывания и оптимизации ML-приложений; сформировать навыки работы с инструментами и методами администрирования, контейнеризации, управления пакетами, ускорения вычислений и обеспечения повторяемости экспериментов в среде Linux.

**2\. Формируемые компетенции**

* LC-5 —Способен применять и (или) проектировать различные инструменты и инженерные практики промышленной разработки, развертывания, эксплуатации и мониторинга систем ИИ.

* LC-5.1. Осуществляет выбор инструментов и инженерных практик промышленной разработки систем ИИ, развертывания и сопровождения моделей МО в продуктивной среде

* Уровень сформированности индикатора компетенции.

* Знает ключевые команды Linux для настройки дистрибутива Linux для задач ML; администрирования GPU-сервера и управления ресурсами; базовые меры безопасности.  
* Имеет представление, как организованы среды разработки (SSH, Jupyter, tmux/screen, виртуальные окружения).

**3\. Основные вопросы**

**Структура лекции**

3.1. Введение (10 мин)

* Роль Linux в ML-экосистеме: серверы, облако, встраиваемые устройства. 

* Требования ML-стека к ОС: стабильность, производительность, поддержка драйверов.

3.2. Выбор дистрибутива и подготовка системы (10 мин)

* Популярные дистрибутивы: Ubuntu LTS, CentOS/ Rocky/ AlmaLinux, Debian.

* Планирование разделов диска, файлы подкачки (swap) vs swapfile, NVMe/SSD особенности.

3.3. Управление пакетами и окружениями (12 мин)

* Системные пакеты: apt/yum/dnf, best practices.

* Среда Python: venv, virtualenv, pip, pipx.

* Среда для ML: Conda (Miniconda), плюсы/минусы conda vs pip.

* Контроль версий библиотек и реплик.

3.4. Драйверы GPU, CUDA и библиотеки ускорения (15 мин)

* Установка драйверов NVIDIA: последовательность (blacklist nouveau, kernel headers, драйвер).  
* Версия CUDA vs версия драйвера vs версии библиотек (cuDNN, NCCL, CUDA Toolkit).  
* Проверка работоспособности: nvidia-smi, nvcc \--version, тестовые скрипты.  
* AMD ROCm кратко.

3.5. Контейнеризация и оркестрация (15 мин)

* Docker/Podman: зачем, отличия, best practices для ML-образов.  
* Создание Dockerfile для ML (базовый образ, CUDA-бейс, минимизация слоёв, кэширование).  
* Управление данными в контейнерах: volume, bind mount, доступ к GPU (nvidia-docker / NVIDIA Container Toolkit).  
* Кратко о Kubernetes, масштабирование ML задач, GPU scheduling.

3.6. Воспроизводимость экспериментов и CI/CD для ML (10 мин)

* Фиксация зависимостей (environment.yml, requirements.txt), lock-файлы.  
* Использование MLflow/DVC для трекинга данных и моделей.  
* Интеграция с CI (GitHub Actions, GitLab CI) для тестирования и сборки образов.

3.8. Мониторинг, логирование и профилирование (8 мин)

* базовый мониторинг ресурсов: top/htop, iotop, iostat, free.

**4\. Ключевые определения (инженерный словарь)**

Docker / контейнеризация: изолированная среда для запуска приложений, использующая образы.

Образ Docker (Docker image): шаблон файловой системы и метаданных, из которого создаются контейнеры.

Контейнер (container): запущенный экземпляр образа.

NVIDIA Container Toolkit (nvidia-docker): расширение для предоставления доступа GPU внутри контейнеров.

CUDA: платформа и набор инструментов для параллельных вычислений на GPU NVIDIA.

cuDNN, NCCL: библиотеки NVIDIA для ускорения нейронных сетей и коммуникаций между GPU.

Conda/Miniconda: менеджер пакетов и сред, распространённый в ML.

Virtualenv / venv: инструменты для изолированных Python-окружений.

cgroups: механизм ядра Linux для ограничения и учёта ресурсов процессов.

Jupyter Notebook / JupyterLab: веб\-интерфейсы для интерактивных вычислений.

MLflow / DVC: инструменты для трекинга экспериментов и управления версиями данных.

CI/CD: непрерывная интеграция и доставка (Continuous Integration / Continuous Delivery).

Reproducibility (воспроизводимость): способность повторить эксперимент при тех же условиях и получить сопоставимые результаты.

Systemd / journald: система инициализации и менеджер журналов в современных Linux.

SSH: Secure Shell для удалённого доступа.

Swap: место подкачки, используется при нехватке ОЗУ.

Kernel headers: заголовки ядра, необходимые для сборки модулей (например, драйверов GPU).

**5\. Ссылки**: 

Официальная документация:

Ubuntu Server Guide – [https://ubuntu.com/server/docs](https://ubuntu.com/server/docs)

Docker Documentation – [https://docs.docker.com](https://docs.docker.com)

NVIDIA CUDA Toolkit Documentation —[https://docs.nvidia.com/cuda](https://docs.nvidia.com/cuda)

NVIDIA Container Toolkit – [https://docs.nvidia.com/datacenter/cloud-native/container-toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit)

Conda docs – [https://docs.conda.io](https://docs.conda.io)

Книги и руководства:

"Linux for Developers" – авторов/изданий по выбору (руководство по практическому использованию Linux).

"Docker Deep Dive" – Nigel Poulton (для понимания контейнеров) \- [https://github.com/nigelpoulton/ddd-book.](https://github.com/nigelpoulton/ddd-book.)

"Systems Performance: Enterprise and the Cloud" – Brendan Gregg (основы мониторинга и профилирования).

Статьи и учебные материалы по ML ops:

MLflow documentation – [https://mlflow.org/docs/latest](https://mlflow.org/docs/latest)

DVC documentation – https://dvc.org/doc

“Best Practices for GPU Cluster Management” – статьи от NVIDIA Developer Blog.

Практические руководства и примеры:

GitHub: официальные Docker образы PyTorch / TensorFlow (пакеты с CUDA): [https://hub.docker.com/r/pytorch/pytorch](https://hub.docker.com/r/pytorch/pytorch), [https://hub.docker.com/r/tensorflow/tensorflow](https://hub.docker.com/r/tensorflow/tensorflow)

Руководства по установке драйверов NVIDIA на Ubuntu (официальные и community HOWTO).

Российские и локальные источники (по желанию преподавателя):

Материалы вузовских курсов по системам и администрированию Linux.

Переводы официальной документации и руководства по CLIs.

**Лекция 2.2. Контейнеризация**

**1\. Цель лекции**  
Сформировать у студентов системное понимание контейнеризации как технологии изоляции и упаковки приложений, её роли в жизненном цикле ML-проектов (разработка, тренировка, инференс, развертывание), а также практические навыки создания, тестирования и эксплуатации контейнеров в Linux-среде для задач ИИ.

**2\. Формируемые компетенции**

*  LC-5 —Способен применять и (или) проектировать различные инструменты и инженерные практики промышленной разработки, развертывания, эксплуатации и мониторинга систем ИИ.

* LC-5.1. Осуществляет выбор инструментов и инженерных практик промышленной разработки систем ИИ, развертывания и сопровождения моделей МО в продуктивной среде

* Уровень сформированности индикатора компетенции.

* Знает, как создавать и собирать Docker-образы для ML (PyTorch/TensorFlow) с CUDA/cuDNN;

* Готов к базовому управлению контейнерами (запуск, остановка, логи, объёмы данных, сети);

* Понимает, как использовать NVIDIA Container Toolkit для доступа к GPU внутри контейнеров;  
* Имеет представление об оптимизации Docker-образов (multistage-build, кэширование слоёв, минимизация размера) и основах оркестрации (Kubernetes, GPU scheduling) и практики CI/CD для ML.

**3\. Основные вопросы**

**Структура лекции**

3.1. Введение: почему контейнеризация важна для ML (10 мин)

* Проблемы традиционного развёртывания: конфликты зависимостей, окружение, версионирование.

* Преимущества контейнеров: переносимость, изоляция, воспроизводимость, масштабируемость.  
* Место контейнеров в ML‑жизненном цикле: локальная разработка → CI/CD → тренировка/инференс.

3.2. Основы контейнеризации: Docker, Podman, runtimes (12 мин)

* Контейнер vs виртуальная машина: различия по архитектуре и производительности.

* Компоненты: Docker Engine, Клиент‑Сервер модель, реестры (Docker Hub, GHCR, частные реестры).  
* Кратко о Podman (daemonless) и других runtime (contained, CRI‑O).

3.3. Работа с образами: создание, сборка (15 мин)

* Dockerfile: структура (FROM, RUN, COPY, ENV, ENTRYPOINT, CMD).  
* Слои и кэширование: как ускорить сборку и уменьшить размер.  
* Выбор базовых образов: slim, alpine vs distroless, CUDA‑базовые образы.  
* Multistage‑build: отделение этапа сборки от финального образа.  
* Ссылка на практический пример: Dockerfile для PyTorch с установкой зависимостей.

3.4. Запуск контейнеров, управление данными и сетями (12 мин)

* Основные команды: docker run, exec, stop, rm, logs, ps.  
* Переменные окружения, аргументы, порты.  
* Тома (volumes) и bind mounts: хранение данных, моделей, датасетов.  
* Сети: bridge, host, none; контейнерное взаимодействие.

3.5. Контейнеры с GPU: доступ к ускорителям (10—12 мин)

* NVIDIA Container Toolkit: установка, демонстрация.  
* Флаги запуска: \--gpus, устройства, переменные.  
* Проверка доступа: nvidia-smi внутри контейнера, тестовые скрипты.  
* Ограничения и совместимость: версии CUDA, драйверы, образы.

3.6. Воспроизводимость экспериментов и ML Ops (10 мин)

* Фиксация зависимостей: environment.yml, requirements.txt, lock-файлы.  
* Трекинг экспериментов: MLflow, DVC, Weights & Biases \- интеграция с контейнерами.  
* CI/CD: сборка образов, тесты, пуш в реестр, автоматическое развертывание.

3.7. Безопасность и ограничения (8 мин)

* Модель безопасности: capabilities, seccomp, AppArmor/SELinux.  
* Запуск от непривилегированного пользователя, minimization attack surface.  
* Сканеры уязвимостей образов (Trivy, Docker Scout).

3.8. Оркестрация и масштабирование (8—10 мин)

* Кратко о Kubernetes: pod, deployment, service, GPU scheduling.  
* Использование GPU в Kubernetes: device plugins, node taints.  
* Практические сценарии: батч‑тренировка, масштабирование инференса.

3.9. Практическая демонстрация (10—15 мин)

* Live demo: сборка Docker-образа, запуск контейнера с GPU, выполнение тренировочного скрипта.  
* Демонстрация воспроизводимости: повторный запуск, сравнение логов.

**4\. Ключевые определения**

Контейнер (container): изолированная среда выполнения приложения, использующая образ.

Образ (image): шаблон, содержащий файловую систему и метаданные, из которого создаётся контейнер.

Dockerfile: текстовый файл с инструкциями для сборки образа.

Слой (layer): неизменяемая часть образа; образы состоят из слоёв.

Multistage build: техника сборки, использующая несколько этапов для уменьшения размера финального образа.

Volume / bind mount: механизмы подключения внешних данных в контейнер.

Docker network: виртуальная сеть для взаимодействия контейнеров (bridge, host, none).

NVIDIA Container Toolkit: расширение Docker, позволяющее контейнерам использовать GPU NVIDIA.

Capability: единица привилегий в Linux; контейнеры могут запускаться с ограниченным набором capabilities.

Seccomp, AppArmor, SELinux: механизмы безопасности для ограничения системных вызовов и политик доступа.

Kubernetes pod: минимальная единица в Kubernetes, содержащая один или несколько контейнеров.

Device plugin (Kubernetes): механизм для предоставления специализированных устройств (например, GPU) контейнерам.

CI/CD: практики непрерывной интеграции и доставки для автоматизации сборки и развертывания.

Reproducibility (воспроизводимость): возможность повторить эксперимент в 

**5\. Ссылки**: 

Перечень источников (рекомендуемая литература и онлайн-ресурсы)

Официальная документация:

Docker Documentation — [https://docs.docker.com](https://docs.docker.com)

Podman Documentation — [https://docs.podman.io](https://docs.podman.io)

NVIDIA Container Toolkit — [https://docs.nvidia.com/datacenter/cloud-native/container-toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit)

Kubernetes Documentation — [https://kubernetes.io/docs](https://kubernetes.io/docs)

Книги и руководства:

“Docker Deep Dive” — Nigel Poulton (практическое руководство по Docker) \- [https://github.com/nigelpoulton/ddd-book](https://github.com/nigelpoulton/ddd-book)

“Container Security” — Liz Rice (безопасность контейнеров).

“Kubernetes Up & Running” — Kelsey Hightower et al. (введение в Kubernetes).

Материалы по ML Ops и воспроизводимости:

MLflow Documentation — [https://mlflow.org/docs](https://mlflow.org/docs)

DVC Documentation — [https://dvc.org/doc](https://dvc.org/doc)

Weights & Biases — [https://wandb.ai/site](https://wandb.ai/site)

Практические ресурсы и примеры:

Официальные Docker-образы PyTorch / TensorFlow: [https://hub.docker.com/r/pytorch/pytorch](https://hub.docker.com/r/pytorch/pytorch), [https://hub.docker.com/r/tensorflow/tensorflow](https://hub.docker.com/r/tensorflow/tensorflow)

Trivy (сканер уязвимостей): [https://github.com/aquasecurity/trivy](https://github.com/aquasecurity/trivy)

Docker Scout (сканер уязвимостей образов Docker): [https://docs.docker.com/scout](https://docs.docker.com/scout)

**6\. Методические указания преподавателю (коротко)**

Перед лекцией подготовить виртуальную машину или облачный инстанс с Docker и NVIDIA драйверами (при наличии GPU).

Демонстрация должна включать примеры:

создание Dockerfile,

сборку образа,

запуск контейнера с GPU,

показать конфигурацию GPU-доступа теоретически.

**Лекция 2.3. Kubernetes**

**1\. Цель лекции**  
Сформировать у студентов системное понимание Kubernetes как платформы оркестрации контейнеров, её роли в жизненном цикле ML=систем (масштабируемая тренировка, инференс, управление ресурсами), а также практические навыки развёртывания, конфигурирования и эксплуатации Kubernetes=кластеров для задач ИИ, включая работу с GPU, сетями, хранилищами и политиками безопасности.

**2\. Формируемые компетенции**

* LC-5 —Способен применять и (или) проектировать различные инструменты и инженерные практики промышленной разработки, развертывания, эксплуатации и мониторинга систем ИИ.

* LC-5.1. Осуществляет выбор инструментов и инженерных практик промышленной разработки систем ИИ, развертывания и сопровождения моделей МО в продуктивной среде

* Уровень сформированности индикатора компетенции.

* Способен развертывать, конфигурировать и поддерживать доступ к GPU в Kubernetes для выполнения вычислений ИИ и использовать HPA (Horizontal Pod Autoscaler) и масштабируемость ML-сервисов.

* Имеет представление о базовом сетевом взаимодействии (Ingress, NetworkPolicy) и управление хранилищами (StatefulSet, PV/PVC).

**3\. Основные вопросы**

**Структура лекции**

3.1. Введение: зачем Kubernetes для ИИ (10 мин)

* Проблемы масштабирования ML-систем: тренировка, инференс, управление ресурсами.  
* Роль Kubernetes: оркестрация, отказоустойчивость, масштабируемость, управление ресурсами.  
* Экосистема: CNCF, инструменты, практики.

3.2. Архитектура Kubernetes (12 мин)

* Контрольная плоскость (control plane): API Server, etcd, Controller Manager, Scheduler.  
* Рабочие узлы (worker nodes): kubelet, kube-proxy, container runtime.  
* Объекты Kubernetes: Pod, Deployment, Service, ConfigMap, Secret, StatefulSet, Job, CronJob.

3.3. Развёртывание кластера (10 мин)

* Локальные решения: kind, minikube, k3d/k3s.  
* Облачные managed‑кластеры: GKE, EKS, AKS, Yandex Managed Kubernetes.  
* Требования к инфраструктуре: CNI, CSI, (device plugins для GPU).

3.4. Работа с объектами: манифесты kubectl (12 мин)

* YAML‑манифесты: Pod, Deployment, Service.  
* kubectl apply, get, describe, logs, exec.  
* ConfigMap и Secret: управление конфигурацией и секретами.  
* Пример: развёртывание ML‑сервиса (инференс) через Deployment \+ Service.

3.5. Доступ к GPU и планирование ресурсов (10 мин)

* NVIDIA Device Plugin: установка и настройка.  
* Запрос ресурсов: limits/requests, спецификация GPU (nvidia.com/gpu).  
* Node taints/tolerations: изоляция GPU‑узлов.  
* Пример YAML: Pod с GPU‑запросом, tolerations.

3.6 Масштабируемость и автомасштабирование (10 мин)

* HPA (Horizontal Pod Autoscaler): метрики CPU, пользовательские метрики.  
* VPA (Vertical Pod Autoscaler), Cluster Autoscaler.  
* Практические сценарии: масштабирование инференс‑сервиса под нагрузку.

3.7. Сети и хранилища (10 мин)

* Сервисы: ClusterIP, NodePort, LoadBalancer.  
* Ingress: маршрутизация трафика, Ingress Controller.  
* NetworkPolicy: сетевая безопасность.  
* Хранилища: PV, PVC, StorageClass, StatefulSet.  
* Пример: развёртывание базы данных/хранилища для модели.

3.8 Мониторинг и логирование (8 мин)

* Metrics Server, Prometheus, Grafana.  
* Логирование: Fluentd/Fluent Bit, Loki, ELK.  
* Мониторинг GPU: DCGM‑exporter, Prometheus \+ Grafana.

3.9. Безопасность и политики (8 мин)

* RBAC (ролевая модель доступа).  
* ServiceAccount, PodSecurityPolicy/PodSecurityAdmission.  
* NetworkPolicy, secrets management.

3.10 CI/CD и GitOps для ML (10 мин)

* Helm: пакеты для развёртывания.  
* GitOps: Argo CD, Flux.  
* Интеграция с MLflow, DVC, W\&B.  
* Сценарий: автоматическое развёртывание ML‑сервиса после обновления модели.

**4\. Ключевые определения**

Kubernetes (K8s): платформа для автоматизации развёртывания, масштабирования и управления контейнеризированными приложениями.

Pod: минимальная единица развёртывания в Kubernetes, содержащая один или несколько контейнеров.

Deployment: объект для управления состоянием ReplicationController и ReplicaSet, обеспечивает развёртывание и обновление.

Service: абстракция для определения набора Pod и доступа к ним (ClusterIP, NodePort, LoadBalancer).

ConfigMap: объект для хранения конфигурационных данных (не секретных).

Secret: объект для хранения конфиденциальных данных (пароли, токены, ключи).

PersistentVolume (PV) / PersistentVolumeClaim (PVC): абстракции для хранения данных, независимые от Pod.

StatefulSet: объект для управления stateful‑приложениями (например, базы данных).

Ingress: объект для управления внешним доступом к сервисам (HTTP/HTTPS).

NetworkPolicy: объект для определения правил сетевого взаимодействия между Pod.

RBAC (Role-Based Access Control): механизм управления доступом на основе ролей.

HPA (Horizontal Pod Autoscaler): механизм автомасштабирования количества Pod.

VPA (Vertical Pod Autoscaler): механизм автомасштабирования ресурсов Pod.

Device Plugin: механизм для предоставления специализированных устройств (например, GPU) Pod.

CNI (Container Network Interface): плагин для настройки сети в Kubernetes.

CSI (Container Storage Interface): плагин для подключения систем хранения.

Helm: менеджер пакетов для Kubernetes.

GitOps: практика управления инфраструктурой через Git (Argo CD, Flux).

**5\. Ссылки**: 

Перечень источников (рекомендуемая литература и онлайн-ресурсы)

Официальная документация:

Kubernetes Documentation — [https://kubernetes.io/docs](https://kubernetes.io/docs)

Helm Documentation — [https://helm.sh/docs](https://helm.sh/docs)

Argo CD Documentation — [https://argo-cd.readthedocs.io](https://argo-cd.readthedocs.io)

NVIDIA Device Plugin for Kubernetes — [https://github.com/NVIDIA/k8s-device-plugin](https://github.com/NVIDIA/k8s-device-plugin)

Книги и руководства:

“Kubernetes Up & Running” — Kelsey Hightower et al. (введение в Kubernetes).

“Cloud Native Patterns” — Cornelia Davis (архитектурные паттерны).

“Kubernetes in Action” — Marko Lukša (практическое руководство).

Материалы по ML Ops и мониторингу:

MLflow Documentation — [https://mlflow.org/docs](https://mlflow.org/docs)

DVC Documentation — [https://dvc.org/doc](https://dvc.org/doc)

Prometheus Documentation — [https://prometheus.io/docs](https://prometheus.io/docs)

Практические ресурсы:

kind (Kubernetes IN Docker) — [https://kind.sigs.k8s.io](https://kind.sigs.k8s.io)

minikube — [https://minikube.sigs.k8s.io](https://minikube.sigs.k8s.io)

Yandex Managed Kubernetes — [https://cloud.yandex.ru/docs/kubernetes](https://cloud.yandex.ru/docs/kubernetes)

**6\. Методические указания преподавателю (коротко)**

Перед лекцией подготовить:

локальный кластер (kind/minikube) или доступ к облачному managed-кластеру;

установленные kubectl, helm, доступ к GPU (при наличии).

Демонстрация должна включать примеры:

создание манифестов Pod, Deployment, Service;

развёртывание ML-сервиса (инференс) и доступ к нему;

настройку GPU-доступа (device plugin, tolerations);

масштабирование (HPA) и мониторинг (Prometheus/Grafana).

При отсутствии GPU можно продемонстрировать:

базовые объекты,

масштабирование,

мониторинг CPU/памяти.

**Лекция 2.4. CI/CD и мониторинг**

**1\. Цель лекции**  
Сформировать у студентов системное понимание практик непрерывной интеграции и доставки (CI/CD) и мониторинга в жизненном цикле ML-систем, а также практические навыки настройки CI/CD-пайплайнов, автоматизации тестирования и развёртывания ML-приложений, и организации мониторинга (метрики, логи, трассировки) для обеспечения надёжности, производительности и наблюдаемости ИИ-систем. 

**2\. Формируемые компетенции**

* LC-5 —Способен применять и (или) проектировать различные инструменты и инженерные практики промышленной разработки, развертывания, эксплуатации и мониторинга систем ИИ.

* LC-5.1. Осуществляет выбор инструментов и инженерных практик промышленной разработки систем ИИ, развертывания и сопровождения моделей МО в продуктивной среде

* Уровень сформированности индикатора компетенции.

* Способен настраивать CI/CD-пайплайны для ML-проектов (GitHub Actions, GitLab CI, Jenkins);

* Знает принципы GitOps; настраивает дашборд Grafana на основе метрик Prometheu

* Знает принципы сбора и анализа логов (ELK, Loki, Fluentd/Fluent Bit).

**3\. Основные вопросы**

3.1. Введение: зачем CI/CD и мониторинг для ИИ (10 мин)

* Проблемы традиционного развёртывания ML: ручные процессы, ошибки, отсутствие наблюдаемости.

* Роль CI/CD: автоматизация, скорость, качество, воспроизводимость.

* Роль мониторинга: надёжность, производительность, обнаружение аномалий.

* Сбор требований (тип задачи, производительность, бюджет, ограничения).

3.2. Основы CI/CD (12 мин)

* Определения: CI (непрерывная интеграция), CD (непрерывная доставка/развёртывание).  
* Компоненты пайплайна: сборка, тестирование, артефакты, развёртывание.  
* Инструменты: GitHub Actions, GitLab CI, Jenkins, CircleCI, Argo CD (GitOps).

3.3. CI/CD для ML: особенности и практики (15 мин)

Отличия ML-пайплайнов: данные, модели, эксперименты.

* Этапы: тестирование кода, валидация данных, тренировка модели, оценка качества, упаковка, развёртывание.  
* Управление артефактами: модели (MLflow, DVC, S3), данные (версионирование).  
* Пример: пайплайн для тренировки и деплоя модели. 

3.4. Практическая настройка CI/CD (12 мин)

* GitHub Actions: workflow, jobs, steps, secrets.  
* GitLab CI: .gitlab-ci.yml, stages, runners.  
* Jenkins: pipelines, declarative syntax.  
* Привести пример: простой пайплайн для ML‑проекта (тесты → сборка образа → деплой).

3.5 Мониторинг: концепции и уровни (10 мин)

* trzy виды наблюдаемости: метрики, логи, трассировки.  
* Уровни мониторинга: инфраструктура, платформа, приложение, бизнес-метрики.  
* Золотые сигналы: задержка, трафик, ошибки, насыщенность.

3.6. Сбор и визуализация метрик (10 мин)

* Prometheus: архитектура, scrape, метрики, правила.  
* Grafana: дашборды, визуализация, алертинг.  
* Экспорт: node-exporter, kube-state-metrics, DCGM-exporter (GPU).  
* Привести пример: дашборд для ML-сервиса.

3.7. Логирование и агрегирование логов (8 мин)

* Источники логов: приложение, система, контейнеры.  
* Стек ELK (Elasticsearch, Logstash, Kibana) и альтернативы (Loki, Fluentd/Fluent Bit).  
* Структурированное логирование: JSON, поля.  
* Привести пример: поиск логов, фильтрация.

3.9. Трассировка и профилирование (8 мин)

* OpenTelemetry: стандарт трассировки, метрик, логов.  
* Jaeger, Zipkin: визуализация трассировок.  
* Профилирование: PyTorch/TensorFlow профайлеры, py-spy, perf.  
* Демо: трассировка запроса в ML-сервисе.

3.10. Алертинг и реагирование (5 мин)

* Настройка алертов: Prometheus Alertmanager, Grafana Alerting.  
* Каналы уведомлений: email, Slack, Telegram.  
* Практики: SLO/SLI, инцидент-менеджмент.

**4\. Ключевые определения**

CI (Continuous Integration): практика частой интеграции кода с автоматическим тестированием.

CD (Continuous Delivery/Deployment): практика автоматического развёртывания кода в среду.

Пайплайн (pipeline): последовательность этапов автоматизации (сборка, тест, деплой).

Артефакт: результат этапа пайплайна (бинарник, Docker-образ, модель).

Runner/Agent: исполнитель заданий в CI/CD (GitHub Actions runner, GitLab runner, Jenkins agent).

Prometheus: система сбора и хранения метрик с языком запросов PromQL.

Grafana: платформа визуализации метрик и алертинга.

ELK Stack: Elasticsearch (поиск/анализ), Logstash (сбор/трансформация), Kibana (визуализация).

Loki: система агрегирования логов, лёгкая альтернатива ELK.

Fluentd/Fluent Bit: сборщики и процессоры логов.

OpenTelemetry: стандарт для сбора телеметрии (метрики, логи, трассировки).

Jaeger: система визуализации распределённых трассировок.

SLO (Service Level Objective): целевой уровень качества сервиса.

SLI (Service Level Indicator): метрика, измеряющая уровень качества.

DCGM-exporter: экспорт метрик GPU NVIDIA в Prometheus.

MLflow: платформа для трекинга экспериментов и управления моделями.

DVC (Data Version Control): инструмент версионирования данных и моделей.

SLO (Service Level Objective): целевой уровень качества сервиса.

SLI (Service Level Indicator): метрика, измеряющая уровень качества.

DCGM-exporter: экспорт метрик GPU NVIDIA в Prometheus.

MLflow: платформа для трекинга экспериментов и управления моделями.

DVC (Data Version Control): инструмент версионирования данных и моделей

**5\. Ссылки**:

Перечень источников (рекомендуемая литература и онлайн-ресурсы)

Официальная документация:

GitHub Actions Documentation — [https://docs.github.com/actions](https://docs.github.com/actions)

GitLab CI/CD Documentation — [https://docs.gitlab.com/ee/ci](https://docs.gitlab.com/ee/ci)

Jenkins Documentation — [https://www.jenkins.io/doc](https://www.jenkins.io/doc)

Argo CD Documentation — [https://argo-cd.readthedocs.io](https://argo-cd.readthedocs.io)

Prometheus Documentation — [https://prometheus.io/docs](https://prometheus.io/docs)

Grafana Documentation — [https://grafana.com/docs](https://grafana.com/docs)

Elasticsearch Documentation — [https://www.elastic.co/guide](https://www.elastic.co/guide)

Loki Documentation — [https://grafana.com/docs/loki](https://grafana.com/docs/loki)

OpenTelemetry Documentation — [https://opentelemetry.io/docs](https://opentelemetry.io/docs)

Jaeger Documentation — [https://www.jaegertracing.io/docs](https://www.jaegertracing.io/docs)

Книги и руководства:

“Continuous Delivery” — Jez Humble, David Farley (классика CI/CD).

“Site Reliability Engineering” — Google SRE Team (надёжность, мониторинг, SLO).

“Kubernetes in Action” — Marko Lukša (раздел про мониторинг и CI/CD).

Материалы по ML Ops:

MLflow Documentation — [https://mlflow.org/docs](https://mlflow.org/docs)

DVC Documentation — [https://dvc.org/doc](https://dvc.org/doc)

“Machine Learning Engineering” — Andriy Burkov (разделы про CI/CD для ML).

Практические ресурсы:

DCGM-exporter (GPU метрики) — [https://github.com/NVIDIA/dcgm-exporter](https://github.com/NVIDIA/dcgm-exporter)

Примеры workflow GitHub Actions для ML — [https://github.com/marketplace?type=actions\&query=ml](https://github.com/marketplace?type=actions&query=ml)

Готовые дашборды Grafana для Kubernetes и ML — [https://grafana.com/grafana/dashboards](https://grafana.com/grafana/dashboards)

**6\. Методические указания преподавателю (коротко)**

Перед лекцией подготовить:

репозиторий с примером ML-проекта (код, тесты, Dockerfile);

настроенный Prometheus \+ Grafana (локально или в Kubernetes);

пример пайплайна (GitHub Actions/GitLab CI).

Демонстрация должна включать примеры:

запуск CI-пайплайна (тесты → сборка образа → пуш в реестр);

развёртывание в Kubernetes (или локально);

показ метрик в Grafana, поиск логов, трассировка запроса.

При отсутствии Kubernetes продемонстрировать:

CI-пайплайн для Docker-образа,

мониторинг метрик приложения (Prometheus client),

логирование и простой дашборд.