📋 Документация: Hub-Satellite Workflow

🎯 Общая концепция

Hub-Satellite модель - это централизованная система управления задачами, где:

Hub (project-hub) - центральный репозиторий для планирования и обсуждения

Satellite (yandex-test, ozon-test, wildberries-test) - репозитории для реализации

Правило №1: Все задачи создаются ТОЛЬКО в Hub!

🚀 Создание задачи

1. Основное создание в Hub
markdown
**Где**: https://github.com/your-org/project-hub/issues/new

**Что указывать**:
- Title: Краткое описание задачи
- Description: Детальное описание, требования, контекст
- Labels: Выбрать соответствующие лейблы (см. раздел ниже)
2. Автоматическое создание в Satellite
После создания задачи в Hub:

Добавьте лейбл satellite/имя-репозитория

satellite/yandex-test

satellite/ozon-test

satellite/wildberries-test

Система автоматически:

Создаст задачу в указанном satellite-репозитории

Добавит в описание Hub-задачи информацию о созданной задаче

Поместит лейбл state/routed в Hub-задачу

🏷️ Система лейблов

Категории лейблов:

1. Satellite назначение

text
satellite/yandex-test     → Задача для Yandex репозитория
satellite/ozon-test       → Задача для Ozon репозитория  
satellite/wildberries-test → Задача для Wildberries репозитория
2. Статусы

text
status/needs-triage - Требует первичного review
status/ready-for-dev - Готово к разработке
status/in-progress - В разработке
status/needs-review - Ожидает code review
status/blocked - Заблокировано
3. Приоритеты

text
priority/critical     → Критический
priority/high         → Высокий
priority/medium       → Средний
priority/low          → Низкий
4. Области (area)

text
area/design-system - Core дизайн-система
area/components - UI компоненты
area/accessibility - A11y и инклюзивность
area/performance - Производительность
area/tooling - Developer experience
5. Типы (type)

text
type/bug - Исправление багов
type/feature - Новая функциональность
type/enhancement - Улучшение существующего
type/refactor - Рефакторинг без изменения API
type/documentation - Документация
type/testing - Тесты и QA
type/ci-cd - CI/CD и автоматизация
6. Системные

text
state/from-hub        → Задача создана из Hub (автоматически)
state/routed          → Задача направлена в satellite (автоматически)

🔄 Автоматическая синхронизация

Что синхронизируется:

Из Hub → Satellite:

✅ Создание задачи при добавлении satellite/ лейбла

✅ Все лейблы (кроме satellite/ и status/need-triage)

✅ Добавление служебных лейблов (state/from-hub)

Из Satellite → Hub:

🔄 Статус задачи (открыта/закрыта)

🔄 Лейблы статусов, приоритетов, областей, типов

💬 Комментарии (кроме системных)

Из Hub → Satellite (обратно):

🔄 Статус задачи (закрытие/переоткрытие)

🔄 Лейблы статусов, приоритетов, областей, типов

💬 Комментарии (кроме системных)

⚠️ Важные ограничения

1. Создание задач

markdown
🚫 НЕЛЬЗЯ: Создавать задачи напрямую в satellite-репозиториях
✅ МОЖНО: Создавать задачи ТОЛЬКО в Hub с satellite-лейблом

2. Синхронизация лейблов

markdown
🔄 Синхронизируются: status/, priority/, area/, type/
🚫 Не синхронизируются: satellite/, state/routed, state/from-hub

3. Комментарии

markdown
🤖 Пропускаются: Системные комментарии, сообщения от ботов
👤 Синхронизируются: Комментарии от пользователей

📋 Пример workflow

Сценарий: Новая функциональность для Yandex

Создание в Hub:

markdown
Title: "Добавить авторизацию через Yandex ID"
Description: "Необходимо реализовать OAuth авторизацию..."
Labels: `satellite/yandex-test`, `type/feature`, `area/backend`, `priority/high`
Автоматические действия:

Создается задача в yandex-test репозитории

В Hub добавляется информация о созданной задаче

Добавляется лейбл state/routed

Работа в Satellite:

Разработчик работает в yandex-test репозитории

Обновляет статусы, добавляет комментарии

Все изменения синхронизируются с Hub

Завершение:

При закрытии задачи в Satellite - она закрывается в Hub

Все комментарии и история сохраняются в обоих местах

🔧 Технические детали

Автоматизации:

🚀 Auto Create in Satellite - создание задач при добавлении satellite-лейбла

🔄 Sync Status from Hub - синхронизация статусов и лейблов

Важно: Все задачи должны проходить через Hub для единого управления и отслеживания!
