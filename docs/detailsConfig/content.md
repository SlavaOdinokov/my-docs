---
sidebar_position: 4
---

Контентная часть поля, представляет собой массив абзацев. Пример:

![Сontent](/img/config/content.jpg)

### content: TemplateContentItem[]

|    Field     |                                  Type                                   | isRequired |               Description                |
| :----------: | :---------------------------------------------------------------------: | :--------: | :--------------------------------------: |
| isBackground |                                 Boolean                                 |   false    |   если true делаем фон текущему абзацу   |
|  paragraph   | (TemplateParagraph \ TemplateParagraphList \ TemplateParagraphSelect)[] |    true    | один абзац состоящий из массива подстрок |
