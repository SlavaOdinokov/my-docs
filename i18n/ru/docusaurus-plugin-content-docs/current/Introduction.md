---
sidebar_position: 1
slug: /
---

# Introduction

Структура конфига:

```js
class TemplateConfig {
  coreConfig: TemplateCoreConfig;
  requisites: TemplateRequisites;
  detailsConfig: TemplateDetailsConfig[];
}
```

|     Field     |          Type           | isRequired |                Description                 |
| :-----------: | :---------------------: | :--------: | :----------------------------------------: |
|  coreConfig   |   TemplateCoreConfig    |    true    |     описывает первый шаг конструктора      |
|  requisites   |   TemplateRequisites    |    true    |         реквизиты сторон контракта         |
| detailsConfig | TemplateDetailsConfig[] |    true    | каждый объект в массиве равен одному блоку |
