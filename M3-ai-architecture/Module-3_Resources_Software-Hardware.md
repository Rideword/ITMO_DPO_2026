Практические занятия по модулю 3

Требования по оборудованию и ПО для выполнения заданий.

Студентам должны быть доступны:

Python 3.8+ и библиотеки: numpy, matplotlib, seaborn (для расчётов Roofline-модели и визуализации).

Transformers, accelerate, bitsandbytes (для загрузки и квантизации LLaMA-3 в NF4/FP4).

AutoGPTQ или готовые GPTQ-чекпоинты моделей на Hugging Face Hub для практики по квантизации.

llama.cpp (собранный из исходников) для конвертации моделей в GGUF, квантизации (Q4_K_M, Q5_K_M, Q8_0) и измерения perplexity.

NVIDIA GPU (рекомендуется от 16 ГБ VRAM для инференса LLaMA-3 8B в FP16; от 8 ГБ для квантованных INT4-версий; CPU-режим приемлем для GGUF-инференса при отсутствии GPU).

NVIDIA Nsight Systems и Nsight Compute для профайлинга (ЛР5).

PyTorch с встроенным torch.profiler для анализа операторов на уровне фреймворка.

Доступ к моделям на Hugging Face Hub (meta-llama/Meta-Llama-3-8B, ISTA-DASLab/Llama-3-8B-Instruct-GPTQ-4bit и др.).

Датасеты WikiText-2 и C4 (загружаются через библиотеку datasets) для измерения perplexity.

Для учебной версии ЛР5 достаточно локального ноутбука с Python и Excel/Matplotlib — расчёты выполняются аналитически без запуска реальной модели. Для ЛР6 при работе с LLaMA-3 8B в FP16 требуется GPU от 16 ГБ VRAM либо облачная платформа (AWS, GCP, Azure, Yandex Cloud, SberCloud); квантованные версии (INT4/GGUF) можно запускать на GPU от 8 ГБ или на CPU.

Рекомендованный набор для выполнения практических занятий

| Компонент | Рекомендация | Зачем |
| :---- | :---- | :---- |
| Расчёты и визуализация | Python, NumPy, Matplotlib | Roofline-диаграмма, таблицы AI/FLOPs (ЛР5) |
| Квантизация (Hugging Face) | Transformers, BitsAndBytes, AutoGPTQ | NF4/FP4/GPTQ-квантизация LLaMA-3 (ЛР6) |
| Квантизация (CPU/Edge) | llama.cpp, GGUF | Q4_K_M-квантизация, измерение perplexity |
| Профайлинг | NVIDIA Nsight Systems, Nsight Compute | Анализ узких мест GPU-ядер |
| Вычислительная платформа | NVIDIA GPU 8–24+ ГБ VRAM либо CPU | Инференс LLaMA-3 8B/70B в разных форматах |
| Датасеты | WikiText-2, C4 (через datasets) | Измерение perplexity моделей |
