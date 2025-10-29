---
name: "\U00002699 General task"
about: Основной функционал
description: Определенное действие или активность, которую необходимо выполнить в репозитории
labels: ["status/need-triage"]
type: Task
body:
  - type: textarea
    id: task-description
    attributes:
      label: Описание
      description: Четкое и детальное описание того, что необходимо выполнить в рамках задачи.
      placeholder: Изменить код с... Переместить утилиту в... Рефакторинг компонента...
    validations:
      required: true
  - type: textarea
    id: additional-context
    attributes:
      label: Дополнительный контекст
      description: Любая другая информация или скриншоты, связанные с задачей.
  - type: checkboxes
    id: checkboxes
    attributes:
      label: Проверки
      description: Перед отправкой issue убедитесь, что выполнили следующее
      options:
        - label: Проверил, что [подобная задача](https://github.com/cdek-it/cdek-ui/issues) еще не была создана, чтобы избежать дублирования.
          required: true
---
