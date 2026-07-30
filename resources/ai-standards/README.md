# Международные стандарты и рамки для AI/ML-систем

## Назначение

Настоящий документ содержит карту международных стандартов и рамок, используемых в дисциплине «Аппаратно-программные платформы для систем искусственного интеллекта» в качестве рекомендательной методической базы. Документы применяются для проектирования, развёртывания, оценивания и сопровождения AI/ML-систем, а также для формирования проектных артефактов студентов.

Данный справочник **не заменяет** полные тексты нормативных документов и не является их официальным переводом. В репозитории размещаются только оригинальные методические материалы, краткие аннотации и ссылки на официальные страницы стандартов.

---

## Карта стандартов дисциплины

| Документ | Статус/тип | Использование в дисциплине | Модули и проект | Учебный артефакт | Официальная ссылка |
|---|---|---|---|---|---|
| ISO/IEC 22989:2022 — Artificial intelligence — Artificial intelligence concepts and terminology | Стандарт | Базовая терминология и глоссарий для всех модулей | M1, M2, M3, M4, Проект | Глоссарий терминов | [ISO 22989](https://www.iso.org/standard/71609.html) |
| ISO/IEC 23053:2022 — Framework for AI systems using machine learning | Стандарт | Референсная структура ML-системы: данные, модель, вычисления, эксплуатация | M1, M2, M3, Проект | Схема архитектуры ML-системы | [ISO 23053](https://www.iso.org/standard/85038.html) |
| ISO/IEC 5338:2023 — Artificial intelligence system life cycle processes | Стандарт | Процессы жизненного цикла AI/ML-системы | M2, M4, Проект | Описание жизненного цикла | [ISO 5338](https://www.iso.org/standard/85039.html) |
| ISO/IEC 23894:2023 — Artificial intelligence — Guidance on risk management | Стандарт | Выявление, оценка, обработка и мониторинг рисков ИИ | M3, M4, Проект | Реестр рисков | [ISO 23894](https://www.iso.org/standard/85037.html) |
| ISO/IEC 42001:2023 — Artificial intelligence management system | Стандарт | Управление AI-системой: роли, документация, контроль изменений, постоянное улучшение | M2, M4, Проект | План управления изменениями | [ISO 42001](https://www.iso.org/standard/92777.html) |
| ISO/IEC 5259-1:2024 и серия ISO/IEC 5259 — Data quality for analytics and machine learning | Стандарт | Качество данных, документация происхождения и ограничений данных | M2, M4, Проект | Паспорт данных | [ISO 5259](https://www.iso.org/standard/94418.html) |
| ISO/IEC 25059:2023 — Software engineering — SQuaRE — Quality model for AI systems | Стандарт | Модель качества AI-систем: качество, надёжность, эффективность, безопасность, объяснимость | M1, M3, M4, Проект | Матрица качества/SLO | [ISO 25059](https://www.iso.org/standard/85036.html) |
| ISO/IEC TR 24028:2020 — Overview of trustworthiness in artificial intelligence | Технический отчёт | Trustworthiness: устойчивость, безопасность, прозрачность, privacy, контролируемость | M4, Проект | Чек-лист trustworthiness | [ISO/TR 24028](https://www.iso.org/standard/71608.html) |
| NIST AI RMF 1.0 — Artificial Intelligence Risk Management Framework | Рамка | Управление рисками ИИ: риски LLM/GenAI, hallucination, prompt injection, privacy, мониторинг | M3, M4, Проект | Чек-лист LLM/GenAI-рисков | [NIST AI RMF](https://www.nist.gov/ai-rmf) |
| NIST AI 600-1:2024 — Generative AI Profile | Рамка | Дополнительная рамка для рисков LLM/GenAI | M3, M4, Проект | Чек-лист LLM/GenAI-рисков | [NIST AI 600-1](https://www.nist.gov/itl/genai-risk-management) |

---

## Применение по модулям

### M1 — Гетерогенные вычислительные платформы

| Стандарт | Применение |
|---|---|
| ISO/IEC 22989 | Единая терминология для описания вычислительных архитектур (CPU, GPU, TPU, FPGA, NPU). |
| ISO/IEC 23053 | Связь компонентов ML-системы с вычислительной платформой. |
| ISO/IEC 25059 | Производительность и эффективность как составляющие качества AI-системы. |

### M2 — Программно-инфраструктурный слой ML-систем

| Стандарт | Применение |
|---|---|
| ISO/IEC 5338 | Процессы жизненного цикла: от подготовки данных до развёртывания и обновления. |
| ISO/IEC 5259 | Управление качеством данных: версионирование, документирование происхождения и ограничений. |
| ISO/IEC 42001 | Роли, документирование, управление изменениями в контексте Docker, CI/CD, MLOps. |
| ISO/IEC 25059 | Эксплуатационные характеристики AI-сервиса: надёжность, масштабируемость, управляемость. |

### M3 — Проектирование вычислительной архитектуры ИИ-систем

| Стандарт | Применение |
|---|---|
| ISO/IEC 23894 | Реестр рисков при выборе архитектуры: latency, throughput, стоимость, энергопотребление. |
| ISO/IEC 23053 | Связь данных, модели и вычислительной платформы при проектировании. |
| ISO/IEC 25059 | Компромисс между качеством, надёжностью, эффективностью и безопасностью AI-системы. |
| NIST AI RMF / GenAI Profile | Оценка рисков LLM-инференса: hallucination, prompt injection, drift. |

### M4 — Промышленный ML-инференс на кластерах и edge-устройствах

| Стандарт | Применение |
|---|---|
| ISO/IEC 5338 | Эксплуатация, мониторинг, обновление и вывод сервиса из эксплуатации. |
| ISO/IEC 23894 | Операционные риски: data drift, сбой инференса, деградация модели. |
| ISO/IEC 5259 | Качество входных данных и мониторинг data drift. |
| ISO/IEC 25059 | SLO/SLA и комплексная оценка качества AI-сервиса. |
| ISO/IEC TR 24028 | Trustworthiness: устойчивость, прозрачность, контролируемость. |
| NIST AI RMF и GenAI Profile | Риски LLM/GenAI: hallucination, prompt injection, leakage, misuse. |

### Проектный кейс

| Стандарт | Применение |
|---|---|
| Все перечисленные | Комплексное применение при разработке, оптимизации, развёртывании и мониторинге ML/LLM-сервиса. |

---

## Правила использования

1. **Доступность.** Студентам не требуется приобретать платные стандарты. В репозитории размещаются только оригинальные методические материалы и ссылки на официальные страницы.
2. **Ссылки.** При подготовке работы студент ссылается на стандарт по номеру и названию (например, «ISO/IEC 23894:2023 — Guidance on risk management»).
3. **Воспроизводимость.** Все решения должны оставаться воспроизводимыми и соответствовать требованиям лицензии репозитория (CC BY-NC-ND 4.0).
4. **Рекомендательный характер.** Стандарты используются как методическая основа и не являются обязательными для сертификации студентов.

---

## Библиографические записи и ссылки

1. ISO/IEC 22989:2022, *Artificial intelligence — Artificial intelligence concepts and terminology*. — URL: <https://www.iso.org/standard/71609.html>
2. ISO/IEC 23053:2022, *Framework for AI systems using machine learning*. — URL: <https://www.iso.org/standard/85038.html>
3. ISO/IEC 5338:2023, *Artificial intelligence system life cycle processes*. — URL: <https://www.iso.org/standard/85039.html>
4. ISO/IEC 23894:2023, *Artificial intelligence — Guidance on risk management*. — URL: <https://www.iso.org/standard/85037.html>
5. ISO/IEC 42001:2023, *Artificial intelligence management system*. — URL: <https://www.iso.org/standard/92777.html>
6. ISO/IEC 5259-1:2024, *Data quality for analytics and machine learning — Part 1: Framework and general requirements*. — URL: <https://www.iso.org/standard/94418.html>
7. ISO/IEC 25059:2023, *Software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Quality model for AI systems*. — URL: <https://www.iso.org/standard/85036.html>
8. ISO/IEC TR 24028:2020, *Overview of trustworthiness in artificial intelligence*. — URL: <https://www.iso.org/standard/71608.html>
9. NIST, *Artificial Intelligence Risk Management Framework (AI RMF) Version 1.0*. — URL: <https://www.nist.gov/ai-rmf>
10. NIST, *AI 600-1: Generative AI Profile for the AI Risk Management Framework*. — URL: <https://www.nist.gov/itl/genai-risk-management>
