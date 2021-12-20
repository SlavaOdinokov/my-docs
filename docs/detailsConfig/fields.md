---
sidebar_position: 3
---

An example for fields inside the block:

![Field_1](/img/config/field_1.jpg)

or

![Field_2](/img/config/field_2.jpg)

### fields: TemplateField[]

|      Field      |         Type          | isRequired |                                                                      Description                                                                       |
| :-------------: | :-------------------: | :--------: | :----------------------------------------------------------------------------------------------------------------------------------------------------: |
|  isBackground   |        Boolean        |   false    |                                                 if it is true, we implement background for this block                                                  |
|      icon       |        String         |   false    |                                                                        icon url                                                                        |
|      title      |        String         |   false    |                                                                         title                                                                          |
| variationsField |   TemplateVariation   |   false    | describes a condition, if the field isn't mandatory or some paragraphs inside the field are not mandatory or variable (can contain several conditions) |
|     content     | TemplateContentItem[] |    true    |                                                                    field's content                                                                     |
|   description   |        String         |   false    |                                                            description for the tooltip (?)                                                             |
|      show       |        Boolean        |   false    |                                 it defines whether we should show the element when we render a page at the first time                                  |
