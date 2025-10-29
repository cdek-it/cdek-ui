---
name: "\U0001F680 Предложение нового функционала"
about: Новая функциональность
description: Предложить новую функциональность для CDEK UI
labels: ["type/feature", "status/need-triage"]
type: Feature
body:
  - type: textarea
    id: feature-description
    attributes:
      label: Описание
      description: Четко и кратко опишите задачу. Постарайтесь максимально детально изложить причины и сценарии использования. Если планируете отправить PR, укажите это в описании. Спасибо!
      placeholder: Я хочу [цель / пожелание], чтобы [получить преимущество].
    validations:
      required: true
  - type: textarea
    id: suggested-solution
    attributes:
      label: Предлагаемое решение
      placeholder: Можно реализовать следующим образом...
    validations:
      required: true
  - type: textarea
    id: alternative
    attributes:
      label: Альтернативы
      description: Четко и кратко опишите альтернативные решения или функции, которые вы рассматривали.
  - type: textarea
    id: additional-context
    attributes:
      label: Дополнительный контекст
      description: Любая другая информация или скриншоты, связанные с запросом функциональности.
  - type: checkboxes
    id: checkboxes
    attributes:
      label: Проверки
      description: Перед отправкой issue убедитесь, что выполнили следующее
      options:
        - label: Проверил, что [подобный запрос](https://github.com/cdek-it/cdek-ui/issues) еще не был создан, чтобы избежать дублирования.
          required: true
---
