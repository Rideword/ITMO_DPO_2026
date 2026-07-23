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
| ЛР7 | NVIDIA Triton / vLLM: развёртывание CV или LLM, нагрузочный тест | Практика | 4 | LC-5, HPC-1 | LC-5.1, HPC-1.2 | Базовый |
| ЛР8 | Финальный кейс: end-to-end обучение → оптимизация → инференс → мониторинг | Практика | 4 | LC-5, HPC-1 | LC-5.1, HPC-1.1, HPC-1.2 | Продвинутый |

## Содержание тем

### 4.1 Серверный инференс

Архитектура серверного ML-инференса. Triton, TorchServe и vLLM; форматы ONNX, TensorRT и GGUF. Dynamic batching, model repository, протоколы HTTP/gRPC и организация сервиса модели.

### 4.2 Оптимизация инференса

Оптимизация LLM-инференса: управление KV-cache, PagedAttention, Flash Attention и speculative decoding. Метрики производительности: TTFT, TPOT, P50/P95/P99 latency, throughput; профилирование сервиса.

### 4.3 Edge AI

Платформы edge AI: NVIDIA Jetson Orin, Hailo-8, мобильные NPU. Форматы и рантаймы TFLite, CoreML и RKNN. Квантизация, энергопотребление, thermal budget, OTA-обновления и автономный инференс.

### 4.4 MLOps для инференса

Практики сопровождения продуктивных моделей: versioning, model registry, мониторинг данных и качества. A/B-тесты, canary-развёртывание, rollback, выявление data/concept drift и организация обратной связи.

## Лабораторные работы

### ЛР7. NVIDIA Triton / vLLM

**Цель:** Развёртывание CV-модели в Triton либо LLM в vLLM. Настройка model repository/API, dynamic batching и лимитов ресурсов. Нагрузочное тестирование, анализ latency/throughput и формирование дашборда метрик.

### ЛР8. Финальный проектный кейс

**Цель:** Комплексный кейс ML Engineer/MLOps: выбор платформы, подготовка модели, оптимизация, контейнеризация и развёртывание сервиса. Мониторинг, логирование, проверка SLA, документирование архитектуры и защита решения.

## Контрольные мероприятия

| № | Вид | Название | Макс. баллы |
|---|---|---|---|
| КТ 6 | Защита | Защита финальной ЛР 8 | 25 |

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
