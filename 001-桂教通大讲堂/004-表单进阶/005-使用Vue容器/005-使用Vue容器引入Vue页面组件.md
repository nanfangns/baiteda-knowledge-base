---
title: "使用Vue容器引入Vue页面组件"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/gc60ted2yg2nb0s6"
visible: true
slug: "gc60ted2yg2nb0s6"
doc_id: 242176239
updated_at: "2025-10-27T06:42:58.000Z"
breadcrumb:
  - "百特搭大讲堂"
  - "表单进阶"
  - "使用Vue容器"
  - "使用Vue容器引入Vue页面组件"
---
<a id="ut34q"></a>


#### 新建Vue容器

<a id="AIlb4"></a>


#### 引用Vue页面，修改Vue容器模版，编写代码


![image.png](../../../_assets/esh4234pkhms3g2f/image-3d5689cce7.png)


```javascript
const ctx = exports.ctx;
const env = exports.env;
const utils = exports.utils;
const pageStatus = utils.getPageStatus()
const http = utils.getHttp(utils.getBasePath());
const isMobile = utils.getDevice() === 'mobile'
const { form_60jg99fo88 } = exports.env.byteluckVuePages
export const vue_name1 = {
  template: `<form_60jg99fo88/>`,
  props: ['instance', 'name', 'value', 'rowIndex', 'pageStatus', 'permissions'],
  emits: ['change'],
  components: { form_60jg99fo88 },
  data: function () {
    return {
    };
  },
  mounted: function () {
    this.$emit('change', 777)//用于更新数据
  },
  methods: {

  }
}
```

<a id="tkkwo"></a>


#### 效果展示


![image.png](../../../_assets/esh4234pkhms3g2f/image-26362a625a.png)
