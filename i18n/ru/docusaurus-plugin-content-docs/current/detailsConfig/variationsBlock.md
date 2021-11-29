---
sidebar_position: 6
---

# variationsBlock/variationsField

С помощью данного раздела осуществляется управление отображением блока/полей или контента внутри них.

### variationsBlock/variationsField: TemplateVariation

|     Field     |          Type           | isRequired |                          Description                           |
| :-----------: | :---------------------: | :--------: | :------------------------------------------------------------: |
| [key: number] | TemplateVariationItem[] |    true    | номер варианта отображения контента внутри поля или всего поля |

:::caution

Тип TemplateVariation не пробрасывается в Swagger (соответственно TemplateVariationItem и TemplateVariationValue так же не пробрасываются), необходимо добавить эти типы вручную.

:::

### :TemplateVariationItem

|    Field    |           Type           | isRequired |         Description         |
| :---------: | :----------------------: | :--------: | :-------------------------: |
|    type     |        ConfigEnum        |    true    |            type             |
|    value    | TemplateVariationValue[] |    true    | массив с вариантами ответов |
|    title    |          String          |    true    |    вопрос или заголовок     |
| description |          String          |   false    | какое-то описание варианта  |

### :TemplateVariationValue

| Field |       Type        | isRequired |                                                                                                                                                               Description                                                                                                                                                                |
| :---: | :---------------: | :--------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| text  |      String       |    true    |                                                                                                                                                      вариант ответа для отображения                                                                                                                                                      |
| next  |      Number       |   false    |                                                                                                                                                   номер следующего вопроса, если есть                                                                                                                                                    |
| value | TemplateParagraph |    true    | вариант ответа, где всегда type: ‘Text’, а value может принимать значения show/hide – в случаи если хотим либо показывать, либо не показывать все поле/блок целиком, либо индексы абзацев из массива content и значение show/hide (пример “0,1-show” или “2,3-hide”) если хотим показывать или скрывать конкретные абзацы внутри content |

### Примеры

Пример 1. Простая вариация, показывать блок или нет, осуществляется с помощью ключевых слов `show/hide`

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

В случаи сложной вариации управление контентом осуществляется по индексам массива content и ключевым словам `show/hide`, которые хранятся в value

```js
value: { type: 'text', value: '0,1-show' },
```

Пример 2. Вариация контента внутри поля

Если пользователь на первый вопрос отвечает `Ja` – скрываем все поле Overwerk, если ответ `Nee` – показываем вопрос 2, если на второй вопрос ответ `Ja` - отображаем paragraph 1 и paragraph 2, если ответ `Nee` - paragraph 3.

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
