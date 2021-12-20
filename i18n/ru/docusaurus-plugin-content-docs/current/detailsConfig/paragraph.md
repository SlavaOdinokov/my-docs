---
sidebar_position: 5
---

Представляет собой массив подстрок. Может быть стандартной строкой, списком или селектом/мультиселектом.

### paragraph: TemplateParagraph[]

|    Field    |    Type    | isRequired |         Description         |
| :---------: | :--------: | :--------: | :-------------------------: |
|    type     | ConfigEnum |    true    |            type             |
|    value    |   String   |    true    |            value            |
|    title    |   String   |   false    | нужен для инпутов, селектов |
| description |   String   |   false    |  описание для тултипа (?)   |
| placeholder |   String   |   false    |         placeholder         |
|    name     |   String   |   false    |       уникальное имя        |
|     br      |  Boolean   |   false    |       перенос строки        |

Пример простой строки с инпутами:

```js
{
  paragraph: [
    {
      type: 'InputNumber',
      value: 'Aantal uur',
      title: 'Hoeveel uur per week gaat de werknemer werken?',
    },
    { type: 'Text', value: ' uur per week verdeeld over: ' },
    {
      type: 'InputNumber',
      value: 'Aantal werkdagen',
      title: 'Hoeveel dagen per week gaat de werknemer werken?',
    },
    { type: 'Text', value: ' werkdagen.' },
  ],
},
```

![Paragraph_1](/img/config/paragraph_1.jpg)

### paragraph: TemplateParagraphList[]

|    Field    |            Type             | isRequired |         Description         |
| :---------: | :-------------------------: | :--------: | :-------------------------: |
|    type     |         ConfigEnum          |    true    |            type             |
|    value    | TemplateParagraphListItem[] |    true    |   массив элементов списка   |
|    title    |           String            |   false    | нужен для инпутов, селектов |
| description |           String            |   false    |  описание для тултипа (?)   |

Пример абзаца со списком:

```js
{
  paragraph: [
    { type: 'Text', value: 'Je krijgt van ons:' },
    {
      type: 'UnorderedList',
      value: [
        {
          listItem: [
            {
              type: 'Text',
              value: 'een reiskostenvergoeding van € 0,19 netto per kilometer of',
            },
          ],
        },
        {
          listItem: [
            { type: 'Text', value: 'een NS abonnement ' },
            {
              type: 'Select',
              markup: 'Text',
              title:
                'Worden reiskosten voor openbaar vervoer vergoed voor eerste of tweede klasse?',
              value: [
                { text: 'eerste klasse', value: 'eerste klasse', type: 'Text' },
                { text: 'tweede klasse', value: 'tweede klasse', type: 'Text' },
              ],
            },
            { type: 'Text', value: ' voor de reizen die je voor werk moet maken' },
          ],
        },
        { listItem: [{ type: 'Text', value: 'een leaseauto' }] },
      ],
    },
  ],
},
```

![Paragraph_2](/img/config/paragraph_2.jpg)

### value: TemplateParagraphListItem

|  Field   |                      Type                       | isRequired |          Description           |
| :------: | :---------------------------------------------: | :--------: | :----------------------------: |
| listItem | (TemplateParagraph / TemplateParagraphSelect)[] |    true    | элемент списка, аналог тега li |

### paragraph: TemplateParagraphSelect[]

|    Field    |             Type              | isRequired |                          Description                          |
| :---------: | :---------------------------: | :--------: | :-----------------------------------------------------------: |
|    type     |          ConfigEnum           |    true    |                             type                              |
|    value    | TemplateParagraphSelectItem[] |    true    |              варианты для селекта/мультиселекта               |
|   markup    |            String             |    true    | вариант отображения селекта/мультиселекта (строка или список) |
|    title    |            String             |   false    |                  нужен для инпутов, селектов                  |
| description |            String             |   false    |                   описание для тултипа (?)                    |

### value: TemplateParagraphSelectItem[]

|    Field    |    Type    | isRequired |        Description        |
| :---------: | :--------: | :--------: | :-----------------------: |
|    text     |   String   |    true    |     описание варианта     |
|    value    |   String   |    true    |     значение варианта     |
|    type     | ConfigEnum |    true    | тип варианта (text/input) |
| placeholder |   String   |   false    |        placeholder        |
|    name     |   String   |   false    |      уникальное имя       |

Пример абзаца с селектом:

```js
{
  paragraph: [
    {
      type: 'Text',
      value:
        'Je zult vertrouwelijke gegevens vertrouwelijk behandelen. Houd je je niet aan deze afspraak, dan moet je een boete betalen. Deze boete is gelijk aan ',
    },
    {
      type: 'Select',
      markup: 'Text',
      title:
        'Hoe hoog is de boete die de werknemer moet betalen als hij het geheimhoudingsbeding overtreedt?',
      value: [
        {
          text: 'een heel jaarsalaris',
          value: 'een heel jaarsalaris',
          type: 'Text',
        },
        {
          text: 'een half jaarsalaris',
          value: 'een half jaarsalaris',
          type: 'Text',
        },
        {
          text: 'anders, namelijk',
          value: 'anders, namelijk',
          type: 'InputString',
        },
      ],
    },
    {
      type: 'Text',
      value:
        ' Daarnaast moet je voor iedere dag dat je je niet houdt aan deze afspraak € 500,- betalen.',
    },
  ],
},
```

![Paragraph_3](/img/config/paragraph_3.jpg)
