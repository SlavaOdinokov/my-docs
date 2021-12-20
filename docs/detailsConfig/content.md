---
sidebar_position: 4
---

Content part of the field is represented as array of paragraphs. Here's the example:

![Сontent](/img/config/content.jpg)

### content: TemplateContentItem[]

|    Field     |                                  Type                                   | isRequired |                                       Description                                       |
| :----------: | :---------------------------------------------------------------------: | :--------: | :-------------------------------------------------------------------------------------: |
|  isDefault   |                                 Boolean                                 |   false    | it defines whether we should show the paragraph when we render a page at the first time |
| isBackground |                                 Boolean                                 |   false    |                  if it is true, we implement background for this block                  |
|  paragraph   | (TemplateParagraph \ TemplateParagraphList \ TemplateParagraphSelect)[] |    true    |                       one pharagraph contains of substring array                        |
