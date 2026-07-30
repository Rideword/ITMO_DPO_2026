# Модуль 4. Промышленный ML-инференс: серверные кластеры и edge-устройства

## Описание модуля

Модуль посвящен промышленному ML-инференсу на серверных кластерах и edge-устройствах: серверный инференс, оптимизация инференса, edge AI, MLOps для инференса.

## Тематический план

| № | Тема | Форма | Объем, ч. | Компетенция | Индикатор | Уровень |
|---|---|---|---|---|---|---|
| 4.1 | Серверный инференс: Triton, TorchServe, vLLM, ONNX/TRT/GGUF, batching | Лекция | 2 | LC-5 | LC-5.1 | Базовый |
| 4.2 | Оптимизация инференса: PagedAttention, Flash Attention, Speculative Decoding, KV-cache | Лекция | 2 | HPC-1 | HPC-1.2 | Базовый |
| 4.3 | Edge AI: Jetson Orin, Hailo-8, TFLite, CoreML, RKNN, OTA | Лекция | 2 | HPC-1 | HPC-1.2 | Базовый |
| 4.4 | MLOps для инференса: model registry, A/B-тест, canary, drift detection | Лекция | 2 | LC-5 | LC-5.1 | Базовый |
| ПР7 | NVIDIA Triton / vLLM: развёртывание CV или LLM, нагрузочный тест | Практика | 4 | LC-5, HPC-1 | LC-5.1, HPC-1.2 | Базовый |
| ПР8 | Финальный кейс: end-to-end обучение → оптимизация → инференс → мониторинг | Практика | 4 | LC-5, HPC-1 | LC-5.1, HPC-1.1, HPC-1.2 | Продвинутый |

## Содержание тем

### 4.1 Серверный инференс

Архитектура серверного ML-инференса. Triton, TorchServe и vLLM; форматы ONNX, TensorRT и GGUF. Dynamic batching, model repository, протоколы HTTP/gRPC и организация сервиса модели.

### 4.2 Оптимизация инференса

Оптимизация LLM-инференса: управление KV-cache, PagedAttention, Flash Attention и speculative decoding. Метрики производительности: TTFT, TPOT, P50/P95/P99 latency, throughput; профилирование сервиса.

### 4.3 Edge AI

Платформы edge AI: NVIDIA Jetson Orin, Hailo-8, мобильные NPU. Форматы и рантаймы TFLite, CoreML и RKNN. Квантизация, энергопотребление, thermal budget, OTA-обновления и автономный инференс.

### 4.4 MLOps для инференса

Практики сопровождения продуктивных моделей: versioning, model registry, мониторинг данных и качества. A/B-тесты, canary-развёртывание, rollback, выявление data/concept drift и организация обратной связи.

## Практические работы

### ПР7. NVIDIA Triton / vLLM

**Цель:** Развёртывание CV-модели в Triton либо LLM в vLLM. Настройка model repository/API, dynamic batching и лимитов ресурсов. Нагрузочное тестирование, анализ latency/throughput и формирование дашборда метрик.

### ПР8. Финальный проектный кейс

**Цель:** Комплексный кейс ML Engineer/MLOps: выбор платформы, подготовка модели, оптимизация, контейнеризация и развёртывание сервиса. Мониторинг, логирование, проверка SLA, документирование архитектуры и защита решения.

## Контрольные мероприятия

| № | Вид | Название | Макс. баллы |
|---|---|---|---|
| КТ 6 | Защита | Защита финальной ПР 8 | 25 |

## Нормативно-методическая связь

Материалы модуля связаны со следующими международными стандартами:

- **ISO/IEC 5338** — эксплуатация, мониторинг, обновление и вывод сервиса из эксплуатации.
- **ISO/IEC 23894** — операционные риски: data drift, сбой инференса, деградация модели.
- **ISO/IEC 5259** — качество входных данных и мониторинг data drift.
- **ISO/IEC 25059** — SLO/SLA и комплексная оценка качества AI-сервиса.
- **ISO/IEC TR 24028** — trustworthiness: устойчивость, прозрачность, контролируемость.
- **NIST AI RMF и GenAI Profile** — риски LLM/GenAI: hallucination, prompt injection, leakage, misuse.

Для практической работы с Triton/vLLM и финального проектного кейса рекомендуется подготовить следующие артефакты: паспорт модели и сервиса, план мониторинга, реестр рисков, чек-лист LLM/GenAI-рисков, план rollback. Данные артефакты интегрируются в существующие критерии оценивания и не требуют дополнительных баллов.

Подробная карта стандартов и учебных артефактов: [resources/ai-standards/README.md](../resources/ai-standards/README.md).

## Ресурсы

- NVIDIA Triton Inference Server documentation
- vLLM documentation
- TorchServe documentation
- MLflow documentation
- Seldon documentation
- Evidently AI documentation
- Jetson documentation
- RKNN Toolkit documentation
- Hailo Developer Zone

## Структура модуля

| Файл | Описание |
|---|---|
| [Конспект лекций](Module-4_Lectures_Konspekt.md) | Подробный конспект по темам 4.1–4.4 |
| [Вопросы к лекциям](Module-4_Lectures_Questions.md) | Вопросы для самопроверки по темам модуля |
| [Руководство по практическим работам](Module-4_Practice_Guide.md) | Инструкции по выполнению ПР7 и ПР8 |
| [Критерии оценки практических работ](Module-4_Practice_Grading.md) | Рубрики и критерии оценивания ПР7 и ПР8 |
| [Ресурсы: ПО и оборудование](Module-4_Resources_Software-Hardware.md) | Список программного обеспечения и аппаратных ресурсов |
| [Руководство для преподавателя](Module-4_Teacher_Lectures_Guide.md) | Методические указания для преподавателя |
| [Тест по модулю](Module-4_Test.md) | Тестовые вопросы для контроля знаний |

