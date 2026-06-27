---
title: "blFormEngineModal 表单弹窗组件"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/gyl6xptiz1ofr1wx"
visible: true
slug: "gyl6xptiz1ofr1wx"
doc_id: 187622053
updated_at: "2024-10-11T06:03:55.000Z"
breadcrumb:
  - "前端开发"
  - "前端内置组件"
  - "blFormEngineModal 表单弹窗组件"
---
<a id="RHeVU"></a>


# 1.属性

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 属性 | 说明 | 类型 | 必填 | 默认值 |
| visible(v-model) | 弹窗是否可见 | boolean |  | false |
| formKey | 表单的formKey | string | 是 |  |
| appId | 应用的appId | string | 是 |  |
| uid | 编辑或查看的的表单uid(唯一标识符) 可以通过value.uid获取 | string |  |  |
| readonly | 是否只读 | boolean |  | false |
| async | 是否需要保存到数据库（true会先调用接口，然后返回数据，false则不调用接口，直接返回数据） | boolean |  | false |
| [onEngineBeforeInit](../002-前端组件属性及事件/005-DataView 表单页/README.md#XXk12) | 表单初始化前的回调方法 | (innerCtx: Engine, payload: EventPayload) => void |  | ​ |
| onEngineMounted | 表单加载完成的回调方法在页面加载完成事件之前触发 | (innerCtx.: Engine) => void |  |  |
| onEngineSubmitted | 表单提交事件，可以拿到弹窗内的表单数据 | (innerCtx: Engine, payload: { value }) => void |  |  |
| onCloseError | 表单关闭时，发现有更改未保存，会触发该回调，若返回false则不关闭弹窗 | () => Promise<void | boolean> |  |  |

<a id="aMA6h"></a>


# 2.示例代码


```javascript
export const createBtn =  {
  template: `<div>
    <a-button type="link" @click="openDailog">创建图书</a-button>
    <bl-form-engine-modal
      v-model:visible="visible"
      form-key="btdev_form_p9djle9ggf"
      app-id="btdev_app_vfuf9ib6zy"
      :readonly="false"
      :on-engine-submitted="onEngineSubmitted"
      :on-engine-mounted="onEngineMounted"
      :on-close-error="onCloseError"
      :onEngineBeforeInit="onEngineBeforeInit"
      async
    ></bl-form-engine-modal>
  </div>`,
  props: ['instance', 'name','value','rowIndex','pageStatus'],
  emits: ['change'],
  data: function () {
    return {
      visible: false
    };
  },
  mounted: function() {
  },
  methods: {
    openDailog: function () {
      this.visible = true
    },
    onEngineSubmitted() {

    },
    onEngineMounted(innerCtx) {
      innerCtx.setState('asc373bsa', ctx.getState('zuyt34f7ka'))
      debugger
    },
    onCloseError() {

    }
  }
}
```
