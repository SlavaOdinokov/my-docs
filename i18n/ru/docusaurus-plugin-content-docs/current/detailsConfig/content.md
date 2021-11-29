---
sidebar_position: 4
---

Контентная часть поля, представляет собой массив абзацев. Пример:

![Сontent](/img/config/content.jpg)

### content: TemplateContentItem[]

|    Field     |                                  Type                                   | isRequired |                          Description                          |
| :----------: | :---------------------------------------------------------------------: | :--------: | :-----------------------------------------------------------: |
|  isDefault   |                                 Boolean                                 |   false    | определяет показывать ли абзац при первом рендеринге страницы |
| isBackground |                                 Boolean                                 |   false    |             если true делаем фон текущему абзацу              |
|  paragraph   | (TemplateParagraph \ TemplateParagraphList \ TemplateParagraphSelect)[] |    true    |           один абзац состоящий из массива подстрок            |
