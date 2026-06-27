---
title: "兼容PC和移动端的Vue容器写法"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/btfnyclckdlk9bde"
visible: true
slug: "btfnyclckdlk9bde"
doc_id: 242176541
updated_at: "2025-10-27T06:42:58.000Z"
breadcrumb:
  - "百特搭大讲堂"
  - "表单进阶"
  - "使用Vue容器"
  - "兼容PC和移动端的Vue容器写法"
---
<a id="Tw9Z8"></a>


#### 新建Vue容器

<a id="emhPY"></a>


#### Vue容器代码

<a id="dBLYX"></a>


##### 示例一


```javascript
const ctx = exports.ctx;
const utils = exports.utils;
const http = utils.getHttp()
const isMobile = utils.getDevice() === 'mobile'

export const DeviceComponent =  {
  template: `<div>
      <div v-if="isMobile">mobile: {{ message }}</div>
      <div v-else>PC: {{ message }}</div>
  </div>
  `,
  props: ['instance', 'name','value','rowIndex','pageStatus','permissions'],
  data: function () {
    return {
      message: 'Hello Vue.js!',
      isMobile: isMobile,
    };
  },
}
```

<a id="woci8"></a>


##### 示例二


```javascript
const ctx = exports.ctx;
const utils = exports.utils;
const http = utils.getHttp()
const isMobile = utils.getDevice() === 'mobile'

// 下方的实例中，通过pageStatus判断了只读状态下展示纯文本，激活状态下可以点击跳转
export const MyComponent =  {
  template: `<ul>
    <li>
        <span v-if="pageStatus === 1">{{ message }}</span>
        <a v-else href="https://www.baidu.com">{{ message }}</a>
    </li>
   </ul>`,
  props: ['instance', 'name','value','rowIndex','pageStatus'],
  data: function () {
    return {
      message: 'Hello Vue.js!'
    };
  },
}
```

<a id="vtS0V"></a>


##### 示例三


```javascript
const ctx = exports.ctx;
const utils = exports.utils;
const http = utils.getHttp()
const isMobile = utils.getDevice() === 'mobile'

export const SubtableDeviceComponent =  {
  template: `<div v-if="pageStatus === 2">
    <a-input v-if="!isMobile" :value="value" @change="updatePCValue"></a-input>
    <van-field v-else :model-value="value" @update:model-value="updateValue"></van-field>
  </div>
  <div v-else>{{value}}</div>
  `,
  props: ['instance', 'name','value','rowIndex','pageStatus'],
  emits: ['change'],
  data: function () {
    return {
      isMobile: isMobile,
    };
  },
  methods: {
    updateValue(value) {
      this.$emit('change', value)
    },
    updatePCValue(e) {
      this.$emit('change', e.target.value)
    }
  }
}
```
