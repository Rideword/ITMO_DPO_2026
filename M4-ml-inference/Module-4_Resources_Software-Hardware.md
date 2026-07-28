Практические занятия по модулю 4

Требования по оборудованию и ПО для выполнения заданий.

Студентам должны быть доступны:

Docker Desktop или Docker Engine на Linux + NVIDIA Container Toolkit для запуска Triton и vLLM в контейнерах.

NVIDIA GPU (рекомендуется от 8–16 ГБ VRAM для лёгких моделей типа Qwen2.5-0.5B/1.5B; от 24 ГБ VRAM для проектных моделей 7B в ПР8).

NVIDIA Triton Inference Server SDK container (nvcr.io/nvidia/tritonserver) для запуска perf_analyzer.

vLLM с OpenAI-совместимым API-сервером (`pip install vllm`).

Python 3.8+ и библиотеки: locust, openai, numpy, matplotlib/seaborn.

Git и GitHub/GitLab для командной работы над проектом (ПР8) с требованием минимум 3 коммитов на участника.

Prometheus + Grafana для мониторинга метрик сервиса в рамках проектного задания.

Доступ к моделям на Hugging Face Hub (Qwen2.5, LLaMA-3, facebook/opt, microsoft/phi-2 и др.).

Для учебной версии ПР7 достаточно одной GPU с 8–16 ГБ VRAM и локального ноутбука для клиентской части (Locust/perf_analyzer). Для проектного кейса (ПР8) при работе с моделями 7B и выше требуется GPU от 24 ГБ VRAM либо доступ к облачной платформе (AWS, GCP, Azure, Yandex Cloud, SberCloud) или GPU-серверу кафедры/индустриального партнёра.

Рекомендованный набор для выполнения практических занятий

| Компонент | Рекомендация | Зачем |
| :---- | :---- | :---- |
| Контейнеризация | Docker, NVIDIA Container Toolkit | Запуск Triton и vLLM в изолированной среде |
| Сервер инференса (мультифреймворк) | NVIDIA Triton Inference Server | Развёртывание модели, perf_analyzer-бенчмаркинг |
| Сервер инференса (LLM) | vLLM (OpenAI-совместимый API) | Быстрый инференс LLM с PagedAttention |
| Нагрузочное тестирование | Locust | Эмуляция пользовательской нагрузки, RPS/latency |
| Вычислительная платформа | NVIDIA GPU 8–24+ ГБ VRAM | Инференс моделей от 0.5B до 7B+ |
| Мониторинг | Prometheus, Grafana | Сбор и визуализация метрик сервиса (проектный кейс) |
| Версионирование | Git, GitHub/GitLab | Совместная разработка проекта, коммиты участников |
