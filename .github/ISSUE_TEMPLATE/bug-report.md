---
name: "\U0001F41E Отчет об ошибке"
about: Исправление багов
color: d73a4a
description: Сообщить о проблеме в CDEK UI
labels: ["type/bug", "status/need-triage"]
type: Bug
body:
  - type: textarea
    id: bug-description
    attributes:
      label: Описание проблемы
      description: Четко и кратко опишите суть ошибки. Если планируете отправить PR для решения этой проблемы, укажите это в описании. Спасибо!
      placeholder: Я выполняю действие ... Ожидаю результат ... Фактически происходит ...
    validations:
      required: true
  - type: input
    id: reproduction
    attributes:
      label: Воспроизведение
      description: |
        Предоставьте ссылку на форк нашего репозитория, где можно воспроизвести проблему.
        Требуется [минимальный пример воспроизведения](https://stackoverflow.com/help/minimal-reproducible-example) ([Почему?](https://antfu.me/posts/why-reproductions-are-required)).
        Если отчет неконкретный (например, только общее сообщение об ошибке) и не содержит примера воспроизведения, ему будет присвоена метка "priority/low". Если пример не будет предоставлен в течение 3 дней, issue будет автоматически закрыт.
      placeholder: URL для воспроизведения
    validations:
      required: true
  - type: textarea
    id: reproduction-steps
    attributes:
      label: Шаги воспроизведения
      description: Опишите последовательность действий для воспроизведения проблемы.
  - type: textarea
    id: environment
    attributes:
      label: Окружение
      description: Укажите вашу операционную систему и браузер
      placeholder: ОС, Браузер
    validations:
      required: true
  - type: checkboxes
    id: checkboxes
    attributes:
      label: Проверки
      description: Перед отправкой issue убедитесь, что выполнили следующее
      options:
        - label: Проверил, что [подобная проблема](https://github.com/cdek-it/cdek-ui/issues) еще не была зарегистрирована, чтобы избежать дублирования.
          required: true
        - label: Предоставленный пример воспроизведения является [минимальным воспроизводимым примером](https://stackoverflow.com/help/minimal-reproducible-example) ошибки.
          required: true
---
