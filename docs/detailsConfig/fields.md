---
sidebar_position: 3
---

Примеры полей внутри блока:

![Field_1](/img/config/field_1.jpg)

или

![Field_2](/img/config/field_2.jpg)

### fields: TemplateField[]

|      Field      |         Type          | isRequired |                                                                      Description                                                                       |
| :-------------: | :-------------------: | :--------: | :----------------------------------------------------------------------------------------------------------------------------------------------------: |
|  isBackground   |        Boolean        |   false    |                                                           если true делаем фон текущему полю                                                           |
|      icon       |     UploadIconDto     |   false    |                                                                     объект иконки                                                                      |
|      title      |        String         |    true    |                                                                         title                                                                          |
| variationsField |   TemplateVariation   |   false    | описывает условия, если поле не обязательно, или какие-либо абзацы внутри поля не обязательны или вариативны (может содержать несколько таких условий) |
|     content     | TemplateContentItem[] |    true    |                                                                      контент поля                                                                      |
|   description   |        String         |   false    |                                                                описание для тултипа (?)                                                                |
