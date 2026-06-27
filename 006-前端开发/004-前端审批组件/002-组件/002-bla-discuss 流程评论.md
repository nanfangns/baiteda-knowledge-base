---
title: "bla-discuss  流程评论"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/srysrq5r66tpg5g4"
visible: true
slug: "srysrq5r66tpg5g4"
doc_id: 187622063
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端审批组件"
  - "组件"
  - "bla-discuss  流程评论"
---
<a id="s9Pnp"></a>


## 效果展示

|  |  |
| --- | --- |
| PC效果 | 移动端效果 |
|

![image.png](../../../_assets/srysrq5r66tpg5g4/image-3ea44f2933.png)

 |

![image.png](../../../_assets/srysrq5r66tpg5g4/image-54fa096a51.png)

 |

<a id="RAVjV"></a>


## 如何使用

- **Vue框架**


```javascript
<template>
  <!-- 具体参数参考上面参数说明，此处只为示例 -->
  <bla-discuss
    ref="discussRef"
    .processInstanceId="processInstanceId"
    .locale="locale"
  ></bla-discuss>
</template>
<script>
import { defineComponent } from "vue";
export default defineComponent({
  setup() {
    const processInstanceId = "0f5b0316-0d69-450e-bf78-ea492ba215bf";
    const locale = "zh";
    return {
      processInstanceId,
      locale,
    };
  },
});
</script>
```

<a id="y29Kt"></a>


## API

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **参数** | **说明** | **类型** | **可选值** | 移动端 |
| process-instance-id | **必选项**，如果参数为异步获取或为空需要在增加判断逻辑 | String | ​ | 支持 |
| locale | 国际化设置，默认为 zh（中文），1.10.0 版本以上支持日语 ja | String | en/zh/ja | 支持 |
| readonly | 是否只读 | Boolean | false/true | 支持 |
