---
sidebar_position: 6
---

# variationsBlock/variationsField

With this section you can manage displaying of blocks/fields or content inside them.

### variationsBlock/variationsField: TemplateVariation

|     Field     |          Type           | isRequired |  Description   |
| :-----------: | :---------------------: | :--------: | :------------: |
| [key: number] | TemplateVariationItem[] |    true    | variant number |

:::caution

TemplateVariation type isn't send at Swagger (TemplateVariationItem and TemplateVariationValue as also), you should add them manually.

:::

### :TemplateVariationItem

|    Field    |           Type           | isRequired |                                      Description                                      |
| :---------: | :----------------------: | :--------: | :-----------------------------------------------------------------------------------: |
|    type     |        ConfigEnum        |    true    |                                         type                                          |
|    value    | TemplateVariationValue[] |    true    |                           an array with options of answers                            |
|    title    |          String          |    true    |                                   question or title                                   |
| description |          String          |   false    |                            some description for the option                            |
|    name     |          String          |   false    |                                      unique name                                      |
|    show     |         Boolean          |   false    | it defines whether we should show the element when we render a page at the first time |

### :TemplateVariationValue

|   Field   |       Type        | isRequired |                                                                                                                                             Description                                                                                                                                              |
| :-------: | :---------------: | :--------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|   text    |      String       |    true    |                                                                                                                                    possible answer for displaying                                                                                                                                    |
|   next    |      Number       |   false    |                                                                                                                              number of the next question, if it exists                                                                                                                               |
|   value   | TemplateParagraph |    true    | answer option, when the type is always 'Text' and the value can be: 1. show/hide - in cases, when we want to define do we show or hide the whole block/field. 2.“0,1-show”/“2,3-hide” where digits are paragraph indexes, which are used to define what paragraph we show inside the 'content' array |
| isDefault |      Boolean      |   false    |                                                                                                        it defines whether we should show the element when we render a page at the first time                                                                                                         |

### Примеры

Example #1: Simple variability, whether we display or don't display, is carried out with the key words `show/hide`

```js
variationsBlock: {
  1: [
    {
      type: 'Radio',
      title: 'Il je een tussentijds opzegbeding opnemen?',
      value: [
        { text: 'Ja', value: { type: 'Text', value: 'show' } },
        { text: 'Nee', value: { type: 'Text', value: 'hide' } },
      ],
      description:
        'Indien je niet afspreekt in het contract dat je tussentijds.',
    },
  ],
},
```

If it is a complex variability, you can manage content with an array index 'content' and key words `show/hide`, which are kept in 'value'

```js
value: { type: 'text', value: '0,1-show' },
```

Example #2: Content variability inside the field

If a user answers `Ja` for the first question, then we hide Overwerk block. If he answers `Nee`, then we show the second question. If a user answers `Ja`, then we display paragraph 1 and paragraph 2. If he answers `Nee`, then we display paragraph 3

```js
{
  title: 'Overwerk',
  description: 'Als er in de cao al afspraken over overwerk.',
  variationsField: {
    1: [
      {
        type: 'Radio',
        title: 'Is er iets over overwerk geregeld in de cao?',
        value: [
          { text: 'Ja', value: { type: 'Text', value: 'hide' } },
          { text: 'Nee', value: { type: 'Text', value: 'hide' }, next: 2 },
        ],
      },
    ],
    2: [
      {
        type: 'Radio',
        title: 'Is overwerk betaald?',
        value: [
          { text: 'Ja', value: { type: 'Text', value: '0,1-show' } },
          { text: 'Nee', value: { type: 'Text', value: '2-show' } },
        ],
      },
    ],
  },
  content: [
    {
      paragraph: [{ type: 'Text', value:'paragraph 1'}],
    },
    {
      paragraph: [{ type: 'Text', value:'paragraph 2'}],
    },
    {
      paragraph: [{ type: 'Text', value:'paragraph 3'}],
    },
  ],
},
```
