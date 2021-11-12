---
sidebar_position: 1
---

Каждый объект в массиве представляет собой один блок.
Пример:

![Block](/img/config/block.jpg)

### detailsConfig: TemplateDetailsConfig[]

|      Field      |        Type         | isRequired |                                                        Description                                                        |
| :-------------: | :-----------------: | :--------: | :-----------------------------------------------------------------------------------------------------------------------: |
|  isBackground   |       Boolean       |   false    |                                            если true делаем фон текущему блоку                                            |
|      title      |       String        |    true    |                                                           title                                                           |
| variationsBlock |  TemplateVariation  |   false    |                                       описывает условие, если блок не обязательный                                        |
|      icon       |    UploadIconDto    |   false    |                                                       объект иконки                                                       |
|     groups      | TemplateGroupItem[] |    true    | объединяет поля блока в группы (нужно для создании иконки группе полей), если иконок нет, то в массиве всегда один объект |
