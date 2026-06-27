---
title: "bla-chatgroup 一键建群"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/uvsahtod9asgs94t"
visible: true
slug: "uvsahtod9asgs94t"
doc_id: 187622069
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端审批组件"
  - "组件"
  - "bla-chatgroup 一键建群"
---
<a id="D4TVd"></a>


## 效果展示

|  |  |
| --- | --- |
| PC效果 | 移动端效果 |
|

![image.png](../../../_assets/uvsahtod9asgs94t/image-f1e7a43ff2.png)

 |  |

<a id="gzf0y"></a>


## 如何使用

- **Vue框架**


```javascript
<template>
  <!-- 具体参数参考上面参数说明，此处只为示例 -->
		<bla-chatgroup
				.locale="locale"
				.processInstanceId="processInstanceId"
    		.bizNum="bizNum"
			></bla-chatgroup>
</template>
<script>
import { defineComponent } from "vue";
export default defineComponent({
  setup() {
    const processInstanceId = "0f5b0316-0d69-450e-bf78-ea492ba215bf";
    const locale = "zh";
    const bizNum="1"
    return {
      processInstanceId,
      locale,
      bizNum
    };
  },
});
</script>
```


​

<a id="baB9L"></a>


## API

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **参数** | **说明** | **类型** | **可选值** | 移动端 |
| process-instance-id | 必选项 | String | ​ | - |
| locale | 国际化设置，默认为 zh（中文) | String | en zh ja | - |
| biz-num | 必选项 单据号 将作为群名称显示 | String | ​ | - |
