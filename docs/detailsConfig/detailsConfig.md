---
sidebar_position: 1
---

Every object in the array is block.
Here is the example:

![Block](/img/config/block.jpg)

### detailsConfig: TemplateDetailsConfig[]

|      Field      |        Type         | isRequired |                                                               Description                                                                |
| :-------------: | :-----------------: | :--------: | :--------------------------------------------------------------------------------------------------------------------------------------: |
|  isBackground   |       Boolean       |   false    |                                          if it is true, we implement background for this block                                           |
|      title      |       String        |   false    |                                                                  title                                                                   |
| variationsBlock |  TemplateVariation  |   false    |                                           it describes a condition, if a block isn't mandatory                                           |
|      icon       |       String        |   false    |                                                                 icon url                                                                 |
|     groups      | TemplateGroupItem[] |    true    | it combines block fields in groups (if we need to set an icon for a group of fields). If there're no icons, an array has only one object |
|      show       |       Boolean       |   false    |                          it defines whether we should show the element when we render a page at the first time                           |
