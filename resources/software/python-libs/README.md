# Python-библиотеки и программные средства

| Название | Аннотация | Связанные КИМ | Доступ | Лицензия / условия | Дата проверки |
|---|---|---|---|---|---|
| NumPy | Базовая библиотека для числовых вычислений (массивы, линейная алгебра). Используется для расчётов FLOPs, VRAM, Roofline-диаграмм. | Модуль 3 | [pypi.org/project/numpy](https://pypi.org/project/numpy) | BSD License | 2026-07-24 |
| Matplotlib | Библиотека визуализации данных. Построение Roofline-диаграмм, графиков производительности и результатов бенчмаркинга. | Модуль 3 | [pypi.org/project/matplotlib](https://pypi.org/project/matplotlib) | BSD License | 2026-07-24 |
| Seaborn | Библиотека визуализации на базе Matplotlib. Улучшенная визуализация результатов профайлинга и бенчмаркинга. | Модуль 3 | [pypi.org/project/seaborn](https://pypi.org/project/seaborn) | BSD License | 2026-07-24 |
| PyTorch | Фреймворк глубокого обучения. Поддержка GPU (CUDA), автодифференцирование, torch.profiler для анализа операторов. | Модуль 1, 3 | [pytorch.org](https://pytorch.org) | BSD License | 2026-07-24 |
| Transformers (Hugging Face) | Библиотека для загрузки и работы с моделями (LLaMA-3, BERT, ResNet). Поддержка квантизации через integrate с BitsAndBytes. | Модуль 3, 4 | [huggingface.co/transformers](https://huggingface.co/transformers) | Apache 2.0 | 2026-07-24 |
| Accelerate (Hugging Face) | Утилиты для ускорения обучения и инференса на GPU/CPU. Поддержка FSDP, mixed precision, многопоточности. | Модуль 3 | [huggingface.co/accelerate](https://huggingface.co/accelerate) | Apache 2.0 | 2026-07-24 |
| BitsAndBytes | Библиотека квантизации моделей (NF4, FP4, INT8). Интеграция с Hugging Face Transformers для снижения VRAM. | Модуль 3 | [github.com/bitsandbytes](https://github.com/bitsandbytes) | Apache 2.0 | 2026-07-24 |
| AutoGPTQ | Инструмент GPTQ-квантизации (4-bit) для LLM. Постобучательная квантизация с компенсацией ошибки. | Модуль 3 | [github.com/AutoGPTQ/AutoGPTQ](https://github.com/AutoGPTQ/AutoGPTQ) | Apache 2.0 | 2026-07-24 |
| datasets (Hugging Face) | Загрузка и обработка датасетов (WikiText-2, C4). Измерение perplexity для оценки качества квантизации. | Модуль 3 | [huggingface.co/datasets](https://huggingface.co/datasets) | Apache 2.0 | 2026-07-24 |
| Pandas | Библиотека для обработки табличных данных. Анализ результатов бенчмаркинга и профилирования. | Модуль 2 | [pypi.org/project/pandas](https://pypi.org/project/pandas) | BSD License | 2026-07-24 |
| scikit-learn | Классическое машинное обучение. Оценка качества моделей, метрики, разделение данных. | Модуль 2 | [scikit-learn.org](https://scikit-learn.org) | BSD License | 2026-07-24 |
| Locust | Инструмент нагрузочного тестирования. Бенчмаркинг пропускной способности и задержки ML-сервисов. | Модуль 4 | [loc.io](https://loc.io) | BSD License | 2026-07-24 |
| OpenAI (Python SDK) | Клиент для OpenAI-совместимого API. Тестирование vLLM-сервера и других инференс-движков. | Модуль 4 | [pypi.org/project/openai](https://pypi.org/project/openai) | Apache 2.0 | 2026-07-24 |

## Требования к добавлению

Фиксируйте версию, команду установки, назначение, совместимость, лицензию и пример минимального использования.
