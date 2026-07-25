# Модуль 3. Проектирование вычислительной архитектуры ИИ-систем

## Описание модуля

Модуль посвящен проектированию вычислительной архитектуры ИИ-систем: методология выбора платформы, расчёт ресурсов, Roofline-модель, распределённое обучение, квантизация и оптимизация.

## Тематический план

| № | Тема | Форма | Объем, ч. | Компетенция | Индикатор | Уровень |
|---|---|---|---|---|---|---|
| 3.1 | Методология выбора аппаратно-программной платформы (HW/SW Co-Design) | Лекция | 2 | HPC-1 | HPC-1.1 | Продвинутый |
| 3.2 | Расчёт ресурсов (Compute Estimation & Profiling) | Лекция | 2 | HPC-1 | HPC-1.2 | Продвинутый |
| 3.3 | Распределённое обучение (Distributed Training) | Лекция | 2 | HPC-1 | HPC-1.2 | Продвинутый |
| 3.4 | Квантизация (Quantization) и сжатие моделей | Лекция | 2 | HPC-1 | HPC-1.2 | Продвинутый |
| ЛР5 | Roofline-анализ: определение compute-bound и memory-bound операций | Практика | 4 | HPC-1 | HPC-1.1, HPC-1.2 | Продвинутый |
| ЛР6 | Расчёт архитектуры LLM: VRAM, пропускная способность, квантизация и перплексия | Практика | 4 | HPC-1 | HPC-1.1, HPC-1.2 | Продвинутый |

## Содержание тем

### 3.1 Методология выбора аппаратно-программной платформы

Треугольник ограничений ИИ-систем: Accuracy, Latency/Throughput, Power & Cost. Триада компромиссов и метод «Жёстких границ» (Hard Constraints). Уровни абстракции кодизайна: Algorithmic, System, Circuit. Матрица принятия решений (Weighted Decision Matrix) по методологии P-C-S-E. Обзор аппаратных платформ: GPU, TPU/NPU, FPGA, Edge ASIC.

### 3.2 Расчёт ресурсов

Оценка объёма памяти для обучения: веса, градиенты, состояния оптимизатора, активации. Расчёт FLOPs для инференса (FC, Conv2D, Attention). Arithmetic Intensity и Roofline Model: ridge point, классификация memory-bound / compute-bound. Инструменты профайлинга: NVIDIA Nsight Systems, Nsight Compute, PyTorch Profiler.

### 3.3 Распределённое обучение

Стратегии параллелизма: Data Parallelism, Pipeline Parallelism, Tensor Parallelism (3D-параллелизм). Коммуникационные библиотеки (NCCL) и коллективные операции (All-Reduce, All-Gather). Законы масштабирования (Амдала, Strong/Weak Scaling). Оптимизаторы для больших батчей (LARS, LAMB). Шардирование состояний (ZeRO-1/2/3, FSDP).

### 3.4 Квантизация и сжатие моделей

Основы квантизации: scale factor, zero point, гранулярность. Post-Training Quantization (PTQ) и Quantization-Aware Training (QAT). Специализированные техники для LLM: SmoothQuant, LLM.int8(), BitNet. Инференсные движки: TensorRT, OpenVINO, GGUF/llama.cpp, ONNX Runtime. Метрики качества: Perplexity (PPL).

## Практические работы

### ЛР5. Roofline-анализ: определение compute-bound и memory-bound операций

**Цель:** Научиться строить Roofline-диаграмму для заданной конфигурации «модель + аппаратная платформа». Освоить расчёт Arithmetic Intensity ключевых операторов нейросети. Определить точку перегиба (ridge point) и классифицировать операторы как compute-bound или memory-bound. Прогнозировать, какой ресурс (FLOPS или память) будет лимитировать производительность.

### ЛР6. Расчёт архитектуры LLM: VRAM, пропускная способность, квантизация и перплексия

**Цель:** Выполнить инженерный расчёт требований к аппаратным ресурсам для инференса LLM (на примере LLaMA-3). Освоить методы квантизации (GPTQ, AWQ, BitsAndBytes, GGUF) для снижения требований к памяти. Измерять и интерпретировать метрику perplexity для оценки потери качества.

## Контрольные мероприятия

| № | Вид | Название | Макс. баллы |
|---|---|---|---|
| Тест по модулю 3 | Тест | Проектирование вычислительной архитектуры ИИ-систем | 20 |

## Требования к оборудованию и ПО

Для выполнения практических занятий необходимы:

- Python 3.8+ и библиотеки: numpy, matplotlib, seaborn, transformers, accelerate, bitsandbytes
- AutoGPTQ или готовые GPTQ-чекпоинты моделей на Hugging Face Hub
- llama.cpp для конвертации моделей в GGUF, квантизации и измерения perplexity
- NVIDIA GPU (от 16 ГБ VRAM для инференса LLaMA-3 8B в FP16; от 8 ГБ для квантованных INT4-версий)
- NVIDIA Nsight Systems и Nsight Compute для профайлинга
- PyTorch с встроенным torch.profiler
- Датасеты WikiText-2 и C4 для измерения perplexity

## Ресурсы

- Williams, Waterman, Patterson. "Roofline: An Insightful Visual Performance Model" (2009)
- AWQ: Activation-aware Weight Quantization (arXiv:2306.00978)
- AutoGPTQ GitHub Repository
- llama.cpp GitHub Repository
- NVIDIA Nsight Systems / Nsight Compute Documentation
- PyTorch FSDP / DeepSpeed ZeRO / Megatron-LM Documentation

## Структура модуля

| Файл | Описание |
|---|---|
| [Конспект лекций](Module-3_Lectures_Konspekt.md) | Подробный конспект по темам 3.1–3.4 |
| [Вопросы к лекциям](Module-3_Lectures_Questions.md) | Вопросы для самопроверки по темам модуля |
| [Руководство по практическим работам](Module-3_Practice_Guide.md) | Инструкции по выполнению ЛР5 и ЛР6 |
| [Критерии оценки практических работ](Module-3_Practice_Grading.md) | Рубрики и критерии оценивания ЛР5 и ЛР6 |
| [Ресурсы: ПО и оборудование](Module-3_Resources_Software-Hardware.md) | Список программного обеспечения и аппаратных ресурсов |
| [Руководство для преподавателя](Module-3_Teacher_Lectures_Guide.md) | Методические указания для преподавателя |
| [Тест по модулю](Module-3_Test.md) | Тестовые вопросы для контроля знаний |
