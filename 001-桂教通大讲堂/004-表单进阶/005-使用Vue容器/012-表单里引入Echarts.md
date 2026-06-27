---
title: "表单里引入Echarts"
node_type: "doc"
source_url: "https://baiteda.yuque.com/czwxoe/wuacuf/frdxei0owz7ad5wz"
visible: true
slug: "frdxei0owz7ad5wz"
doc_id: 187621915
updated_at: "2024-09-24T03:56:38.000Z"
breadcrumb:
  - "百特搭大讲堂"
  - "表单进阶"
  - "使用Vue容器"
  - "表单里引入Echarts"
---
1、表单里拖一个Vue容器


![image.png](../../../_assets/frdxei0owz7ad5wz/image-571907ada9.png)


2、Vue容器内代码


```javascript
const ctx = exports.ctx;
const utils = exports.utils;
const http = utils.getHttp()
const isMobile = utils.getDevice() === 'mobile'
export const e_charts = {
  template: `
      <div id="main" class="charts-content"></div>
  `,
  props: ['instance', 'name', 'value', 'rowIndex', 'pageStatus', 'permissions'],
  emits: ['change'],
  data: function () {
    return {

    };
  },
  mounted: function () {
    this.initCharts()
  },
  methods: {
    initCharts() {
      let url = 'https://cdnjs.cloudflare.com/ajax/libs/echarts/5.4.1/echarts.min.js';
      let jsapi = document.createElement('script');
      jsapi.charset = 'utf-8';
      jsapi.src = url;
      jsapi.onload = async () => {
        this.drawCharts()
      }
      document.head.appendChild(jsapi);
    },
    drawCharts() {
      var chartDom = document.getElementById('main');
      var myChart = echarts.init(chartDom);
      var option;
      option = {
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            data: [150, 230, 224, 218, 135, 147, 260],
            type: 'line'
          }
        ]
      };
      option && myChart.setOption(option);
    }
  }
}
```


3、预览效果


![image.png](../../../_assets/frdxei0owz7ad5wz/image-c4379cbba7.png)
