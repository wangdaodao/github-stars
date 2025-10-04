---
project: v-charts
stars: 6806
description: 基于 Vue2.0 和 ECharts 封装的图表组件📈📊
url: https://github.com/ElemeFE/v-charts
---

### v-charts

Document | Sample Project | English | 中文

> Chart components based on Vue2.x and Echarts

Features
--------

-   **Uniform data format:** Use an uniform data format that both convient for frontend and backend, and also easy to create and edit.
-   **Simplified configuration:** With simplified configuration items, complex requirements can be easily implemented.
-   **Simple customization:** Provide a variety of custom Echarts way, you can easily set the chart options.

Support
-------

Modern browsers and Internet Explorer 10+, include pc and mobile browser.

Install
-------

```
npm i v-charts echarts -S
```

Start
-----

<template\>
  <div\>
    <ve-line :data\="chartData"\></ve-line\>
  </div\>
</template\>

<script\>
import VeLine from 'v-charts/lib/line.common'
export default {
  components: { VeLine },
  data () {
    return {
      chartData: {
        columns: \['date', 'PV'\],
        rows: \[
          { 'date': '01-01', 'PV': 1231 },
          { 'date': '01-02', 'PV': 1223 },
          { 'date': '01-03', 'PV': 2123 },
          { 'date': '01-04', 'PV': 4123 },
          { 'date': '01-05', 'PV': 3123 },
          { 'date': '01-06', 'PV': 7123 }
        \]
      }
    }
  }
}
</script\>

Changelog
---------

Detailed changes for each release are documented in the release notes or ChangeLog.

Contribution
------------

Please make sure to read the Contributing Guide before making a pull request.

License
-------

MIT
