Практические занятия по модулю 1

Требования по оборудованию и ПО для выполнения заданий (ПР1. Профилирование GPU; ПР2. Бенчмаркинг платформ).

Студентам должны быть доступны:

ПК/ноутбук или сервер с Ubuntu 22.04 LTS и NVIDIA GPU (RTX 3060+, от 8 ГБ VRAM); драйверы NVIDIA и CUDA Toolkit 12.x.

Python 3.11+ и PyTorch 2.x с поддержкой CUDA.

NVIDIA DCGM (Data Center GPU Manager) для расширенного мониторинга GPU (SM Activity, Tensor Core Utilization, PCIe/NVLink throughput).

PyTorch Profiler (`torch.profiler`) и TensorBoard для визуализации трасс профилирования.

Тестовые модели: `torchvision.models.resnet50` и/или `bert-base-uncased` (Hugging Face Transformers).

Доступ к бенчмаркам MLPerf/MLCommons для сопоставления измеренных показателей с эталонными значениями.

Доступ к GPU-серверу предоставляется кафедрой/индустриальным партнёром ВУЗа при отсутствии GPU на локальном устройстве студента.

Для учебной версии достаточно одной GPU с 8+ ГБ VRAM и локального окружения Python; расширенные бенчмарки (batch=128, FP16 с Tensor Cores) требуют GPU с поддержкой Tensor Cores (RTX 30xx/40xx, A100 и новее).

Рекомендованный набор для выполнения практических занятий

| Компонент | Рекомендация | Зачем |
| :---- | :---- | :---- |
| Вычислительная платформа | NVIDIA GPU RTX 3060+ (от 8 ГБ VRAM), CUDA 12.x | Обучение/инференс тестовых моделей, профилирование и бенчмаркинг |
| Мониторинг | nvidia-smi, NVIDIA DCGM | Метрики утилизации GPU, памяти, температуры, TDP |
| Профилирование | PyTorch Profiler (`torch.profiler`), TensorBoard | Анализ времени по операторам, трассы CPU/GPU (ПР1) |
| Бенчмаркинг | `torch.utils.benchmark` или собственные скрипты замера | Измерение latency/throughput по batch size и precision (ПР2) |
| Тестовые модели | ResNet-50 (torchvision), BERT-base (Hugging Face) | Объект профилирования и бенчмаркинга |
| Эталонные данные | MLPerf / MLCommons benchmark reports | Сопоставление измеренных показателей с эталоном |
