---
sidebar_position: 7
---

# Types

```js
enum ConfigEnum {
  Text = 'Text',
  Title = 'Title',
  Datepicker = 'Datepicker',
  UnorderedList = 'UnorderedList',
  OrderedList = 'OrderedList',
  Radio = 'Radio',
  Select = 'Select',
  MultiSelect = 'MultiSelect',
  InputString = 'InputString',
  InputNumber = 'InputNumber',
}

class TemplateColors {
  main: string
  accent: string
  background: string
}

class TemplateStyle {
  fontFamily: string
  fontSize: string
  fontStyle: string
  fontWeight: string
}

class TemplateCoreConfig {
  colors: TemplateColors
  headings: TemplateStyle
  bodyText: TemplateStyle
  isBackground?: boolean
}

class TemplateParagraph {
  type: ConfigEnum
  value: string
  title?: string
  description?: string
}

class TemplateVariationValue {
  text: string
  value: TemplateParagraph
  next?: number
}

class TemplateVariationItem {
  type: ConfigEnum
  title: string
  value: TemplateVariationValue[]
  description?: string
}

class TemplateVariation {
  [key: number]: TemplateVariationItem[]
}

class TemplateParagraphSelectItem {
  text: string
  value: string
  type: string
}


class TemplateParagraphSelect {
  type: ConfigEnum
  markup: string
  value: TemplateParagraphSelectItem[]
  title?: string
  description?: string
}

class TemplateParagraphListItem {
  listItem: (TemplateParagraph | TemplateParagraphSelect)[]
}

class TemplateParagraphList {
  type: ConfigEnum
  value: TemplateParagraphListItem[]
  title?: string
  description?: string
}

class TemplateContentItem {
  isBackground?: boolean
  isDefault?: boolean
  paragraph: (TemplateParagraph | TemplateParagraphList | TemplateParagraphSelect)[]
}

class TemplateField {
  isBackground?: boolean
  title: string
  icon?: string
  variationsField?: TemplateVariation
  content: TemplateContentItem[]
  description?: string
}

class TemplateGroupItem {
  isBackground?: boolean
  icon?: string
  fields: TemplateField[]
}

class TemplateDetailsConfig {
  isBackground?: boolean
  title: string
  variationsBlock?: TemplateVariation
  icon?: string
  groups: TemplateGroupItem[]
}

class TemplateRequisitesColumn {
  title: string
  content: TemplateParagraph[]
}

class TemplateRequisitesFooter {
  leftColumn: TemplateRequisitesColumn
  rightColumn: TemplateRequisitesColumn
}

class TemplateRequisites {
  header: TemplateParagraph[]
  footer: TemplateRequisitesFooter
}

class TemplateConfig {
  coreConfig: TemplateCoreConfig
  requisites: TemplateRequisites
  detailsConfig: TemplateDetailsConfig[]
}
```
