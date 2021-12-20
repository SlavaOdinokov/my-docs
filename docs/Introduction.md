---
sidebar_position: 1
slug: /
---

# Introduction

Configuration structure:

```js
class TemplateConfig {
  coreConfig: TemplateCoreConfig;
  requisites: TemplateRequisites;
  detailsConfig: TemplateDetailsConfig[];
}
```

|     Field     |          Type           | isRequired |                   Description                    |
| :-----------: | :---------------------: | :--------: | :----------------------------------------------: |
|  coreConfig   |   TemplateCoreConfig    |    true    | describes the first step of the Contract Builder |
|  requisites   |   TemplateRequisites    |    true    |   details of parties involved in the contract    |
| detailsConfig | TemplateDetailsConfig[] |    true    |       every object in the array is a block       |
