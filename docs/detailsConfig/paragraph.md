---
sidebar_position: 5
---

It is an array of substrings. It can be a string, list or select / multi select field.

### paragraph: TemplateParagraph[]

|    Field    |    Type    | isRequired |                 Description                 |
| :---------: | :--------: | :--------: | :-----------------------------------------: |
|    type     | ConfigEnum |    true    |                    type                     |
|    value    |   String   |    true    |                    value                    |
|    title    |   String   |   false    | it is required for inputs and select fields |
| description |   String   |   false    |       description for the tooltip (?)       |
| placeholder |   String   |   false    |                 placeholder                 |
|    name     |   String   |   false    |                 unique name                 |
|     br      |  Boolean   |   false    |                 line break                  |

An example of the simple string with inputs:

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

|    Field    |            Type             | isRequired |                 Description                 |
| :---------: | :-------------------------: | :--------: | :-----------------------------------------: |
|    type     |         ConfigEnum          |    true    |                    type                     |
|    value    | TemplateParagraphListItem[] |    true    |           an array of items list            |
|    title    |           String            |   false    | it is required for inputs and select fields |
| description |           String            |   false    |       description for the tooltip (?)       |

An example of the paragraph with list:

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

|  Field   |                      Type                       | isRequired |                  Description                   |
| :------: | :---------------------------------------------: | :--------: | :--------------------------------------------: |
| listItem | (TemplateParagraph / TemplateParagraphSelect)[] |    true    | list element, which is an analogue of "li" tag |

### paragraph: TemplateParagraphSelect[]

|    Field    |             Type              | isRequired |                          Description                           |
| :---------: | :---------------------------: | :--------: | :------------------------------------------------------------: |
|    type     |          ConfigEnum           |    true    |                              type                              |
|    value    | TemplateParagraphSelectItem[] |    true    |           options for select and multi select fields           |
|   markup    |            String             |    true    | option for displaying select and multi select (string or list) |
|    title    |            String             |   false    |          it is required for inputs and select fields           |
| description |            String             |   false    |                description for the tooltip (?)                 |

### value: TemplateParagraphSelectItem[]

|    Field    |    Type    | isRequired |        Description        |
| :---------: | :--------: | :--------: | :-----------------------: |
|    text     |   String   |    true    |    option description     |
|    value    |   String   |    true    |       option value        |
|    type     | ConfigEnum |    true    | variant type (text/input) |
| placeholder |   String   |   false    |        placeholder        |
|    name     |   String   |   false    |        unique name        |

An example of the paragraph with select field:

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
