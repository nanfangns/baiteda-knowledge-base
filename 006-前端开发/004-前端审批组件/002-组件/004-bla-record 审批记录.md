---
title: "bla-record 审批记录"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/dpxcgtzh9v0mtqkz"
visible: true
slug: "dpxcgtzh9v0mtqkz"
doc_id: 187622068
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "前端开发"
  - "前端审批组件"
  - "组件"
  - "bla-record 审批记录"
---
<a id="zDYNM"></a>


## 效果展示

|  |  |
| --- | --- |
| PC效果 | 移动端效果 |
|

![image.png](../../../_assets/dpxcgtzh9v0mtqkz/image-11c829266a.png)

 |

![image.png](../../../_assets/dpxcgtzh9v0mtqkz/image-dd3c4560e0.png)

 |

<a id="lKCaJ"></a>


## 如何使用

- **Vue框架**


```javascript
<template>
  <!-- 具体参数参考上面参数说明，此处只为示例 -->
		<bla-record
				.locale="locale"
				.processInstanceId="processInstanceId"
				.innerStyle="{ borderRadius: '8px' }"
			></bla-record>
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

<a id="hmnqO"></a>


## API

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **参数** | **说明** | **类型** | **可选值** | 移动端 |
| process-instance-id | 必选项 | String | ​ | 支持 |
| locale | 国际化设置，默认为 zh（中文），1.10.0 版本以上支持日语 ja | String | en zh ja | 支持 |
| show-selection | 是否开启多选 | Boolean | false true | - |
| show-operation-column | 是否显示操作列 | Boolean | false true | - |
