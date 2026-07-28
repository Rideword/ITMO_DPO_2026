# Бенчмарки и бейзлайны

Раздел содержит открытые бенчмарки и бейзлайны, используемые для сравнения аппаратных платформ, оценки производительности инференса и обучения, а также для практических занятий и проектной работы по модулям 1, 3 и 4.

| Название | Аннотация | Связанные КИМ | Доступ | Лицензия / условия | Дата проверки |
|---|---|---|---|---|---|
| MLPerf Inference | Индустриальный бенчмарк-сьют для оценки производительности инференса на разных аппаратных платформах (CPU, GPU, TPU, NPU, edge). Используется как источник количественных данных для сравнительной матрицы платформ | [Модуль 1. Практика](../../M1-heterogeneous-platforms/Module-1_Practice_Guide.md) | [mlcommons.org/benchmarks](https://mlcommons.org/benchmarks/) | Открытая методология MLCommons, свободное использование результатов с указанием источника | [2026-07-28] |
| MLPerf Training | Бенчмарк-сьют для оценки времени и стоимости обучения моделей (ResNet, BERT, LLM) на различных конфигурациях кластеров | [Модуль 3. Лекции](../../M3-ai-architecture/Module-3_Lectures_Konspekt.md) | [mlcommons.org/benchmarks/training](https://mlcommons.org/benchmarks/training/) | Открытая методология MLCommons | [2026-07-28] |
| NVIDIA Triton `perf_analyzer` (эталонные прогоны) | Встроенный инструмент бенчмаркинга Triton Inference Server: throughput/latency при разных уровнях параллелизма и batch size. Используется как бейзлайн для практической работы 7 | [Модуль 4. Практика, ПЗ7](../../M4-ml-inference/Module-4_Practice_Guide.md) | [github.com/triton-inference-server/server](https://github.com/triton-inference-server/server) | Apache 2.0 | [2026-07-28] |
| vLLM Benchmark Suite | Официальные скрипты нагрузочного тестирования vLLM (throughput, TTFT, TPOT) для сравнения конфигураций инференса LLM | [Модуль 4. Практика, ПЗ7](../../M4-ml-inference/Module-4_Practice_Guide.md) | [github.com/vllm-project/vllm/tree/main/benchmarks](https://github.com/vllm-project/vllm/tree/main/benchmarks) | Apache 2.0 | [2026-07-28] |
| LLaMA-3 Perplexity Baselines (WikiText-2, C4) | Опубликованные значения perplexity для LLaMA-3 8B/70B в разных форматах (FP16, INT8, INT4) — точка отсчёта при оценке потерь качества после квантизации | [Модуль 3. Практика, ПР6](../../M3-ai-architecture/Module-3_Practice_Guide.md) | [huggingface.co/meta-llama](https://huggingface.co/meta-llama) | Meta LLaMA-3 Community License | [2026-07-28] |
| Roofline Model эталонные конфигурации GPU | Паспортные данные Peak FLOP/s и Peak Bandwidth для NVIDIA A100, H100, RTX 4090, Jetson Orin — базовые значения для расчёта Ridge Point на ПР5 | [Модуль 3. Практика, ПР5](../../M3-ai-architecture/Module-3_Practice_Guide.md) | [nvidia.com/en-us/data-center](https://www.nvidia.com/en-us/data-center/) | Официальная документация производителя | [2026-07-28] |

## Требования к добавлению

При добавлении нового бенчмарка в таблицу необходимо указать:

- **Задачу** — что именно измеряется (инференс, обучение, квантизация, throughput/latency и т. д.).
- **Метрики** — конкретные показатели (RPS, latency p50/p95/p99, TTFT, TPOT, FLOP/s, perplexity, accuracy).
- **Протокол эксперимента** — конфигурация железа, batch size, длина последовательности, число прогонов, способ усреднения результатов.
- **Базовые решения (бейзлайны)** — с чем сравнивается результат (референсная платформа, референсная модель, референсный формат).
- **Требования к воспроизводимости** — версии ПО/драйверов, фиксация random seed, доступность скриптов запуска.
- **Правила сравнения** — допустимые и недопустимые сопоставления результатов (например, нельзя сравнивать latency при разных batch size без нормализации).
