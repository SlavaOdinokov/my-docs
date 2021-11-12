---
sidebar_position: 2
---

Пример группы полей, одна иконка объединяет два поля:

![Groups](/img/config/groups.jpg)

### groups: TemplateGroupItem[]

|    Field     |      Type       | isRequired |                Description                |
| :----------: | :-------------: | :--------: | :---------------------------------------: |
| isBackground |     Boolean     |   false    | если true делаем фон текущей группе полей |
|     icon     |  UploadIconDto  |   false    |               объект иконки               |
|    fields    | TemplateField[] |    true    |             поля внутри блока             |
