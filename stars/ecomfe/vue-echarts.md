---
project: vue-echarts
stars: 10276
description: Vue.js component for Apache ECharts™.
url: https://github.com/ecomfe/vue-echarts
---

Vue ECharts
===========

Vue.js component for Apache ECharts™.

> Still using Vue 2? Read v7 docs here →

Installation & Usage
--------------------

### npm

npm install echarts vue-echarts

#### Example

Demo →

<template\>
  <v-chart class\="chart" :option\="option" />
</template\>

<script setup>
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { PieChart } from "echarts/charts";
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent,
} from "echarts/components";
import VChart, { THEME\_KEY } from "vue-echarts";
import { ref, provide } from "vue";
use(\[
  CanvasRenderer,
  PieChart,
  TitleComponent,
  TooltipComponent,
  LegendComponent,
\]);
provide(THEME\_KEY, "dark");
const option \= ref({
  title: {
    text: "Traffic Sources",
    left: "center",
  },
  tooltip: {
    trigger: "item",
    formatter: "{a} <br/>{b} : {c} ({d}%)",
  },
  legend: {
    orient: "vertical",
    left: "left",
    data: \["Direct", "Email", "Ad Networks", "Video Ads", "Search Engines"\],
  },
  series: \[
    {
      name: "Traffic Sources",
      type: "pie",
      radius: "55%",
      center: \["50%", "60%"\],
      data: \[
        { value: 335, name: "Direct" },
        { value: 310, name: "Email" },
        { value: 234, name: "Ad Networks" },
        { value: 135, name: "Video Ads" },
        { value: 1548, name: "Search Engines" },
      \],
      emphasis: {
        itemStyle: {
          shadowBlur: 10,
          shadowOffsetX: 0,
          shadowColor: "rgba(0, 0, 0, 0.5)",
        },
      },
    },
  \],
});
</script\>

<style scoped>
.chart {
  height: 400px;
}
</style\>

Important

We encourage manually importing components and charts from ECharts for smaller bundle size. We've built an import code generator to help you with that. You can just paste in your `option` code and we'll generate the precise import code for you.

Try it →

But if you really want to import the whole ECharts bundle without having to import modules manually, just add this in your code:

import "echarts";

### CDN

Drop `<script>` inside your HTML file and access the component via `window.VueECharts`.

Demo →

<script src\="https://cdn.jsdelivr.net/npm/echarts@6.0.0"\></script\>
<script src\="https://cdn.jsdelivr.net/npm/vue@3.5.18"\></script\>
<script src\="https://cdn.jsdelivr.net/npm/vue-echarts@8.0.0-beta.1"\></script\>

const app \= Vue.createApp(...)

// register globally (or you can do it locally)
app.component('v-chart', VueECharts)

See more examples here.

### Props

-   `init-options: object`
    
    Optional chart init configurations. See `echarts.init`'s `opts` parameter here →
    
    Injection key: `INIT_OPTIONS_KEY`.
    
-   `theme: string | object`
    
    Theme to be applied. See `echarts.init`'s `theme` parameter here →
    
    Injection key: `THEME_KEY`.
    
-   `option: object`
    
    ECharts' universal interface. Modifying this prop will trigger ECharts' `setOption` method. Read more here →
    
    > 💡 When `update-options` is not specified, `notMerge: false` will be specified by default when the `setOption` method is called if the `option` object is modified directly and the reference remains unchanged; otherwise, if a new reference is bound to `option`, `notMerge: true` will be specified.
    
-   `update-options: object`
    
    Options for updating chart option. See `echartsInstance.setOption`'s `opts` parameter here →
    
    Injection key: `UPDATE_OPTIONS_KEY`.
    
-   `group: string`
    
    Group name to be used in chart connection. See `echartsInstance.group` here →
    
-   `autoresize: boolean | { throttle?: number, onResize?: () => void }` (default: `false`)
    
    Whether the chart should be resized automatically whenever its root is resized. Use the options object to specify a custom throttle delay (in milliseconds) and/or an extra resize callback function.
    
-   `loading: boolean` (default: `false`)
    
    Whether the chart is in loading state.
    
-   `loading-options: object`
    
    Configuration item of loading animation. See `echartsInstance.showLoading`'s `opts` parameter here →
    
    Injection key: `LOADING_OPTIONS_KEY`.
    
-   `manual-update: boolean` (default: `false`)
    
    For performance critical scenarios (having a large dataset) we'd better bypass Vue's reactivity system for `option` prop. By specifying `manual-update` prop with `true` and not providing `option` prop, the dataset won't be watched any more. After doing so, you need to retrieve the component instance with `ref` and manually call `setOption` method to update the chart.
    

### Events

You can bind events with Vue's `v-on` directive.

<template\>
  <v-chart :option\="option" @highlight\="handleHighlight" />
</template\>

Note

Only the `.once` event modifier is supported as other modifiers are tightly coupled with the DOM event system.

Vue ECharts support the following events:

-   `highlight` →
-   `downplay` →
-   `selectchanged` →
-   `legendselectchanged` →
-   `legendselected` →
-   `legendunselected` →
-   `legendselectall` →
-   `legendinverseselect` →
-   `legendscroll` →
-   `datazoom` →
-   `datarangeselected` →
-   `timelinechanged` →
-   `timelineplaychanged` →
-   `restore` →
-   `dataviewchanged` →
-   `magictypechanged` →
-   `geoselectchanged` →
-   `geoselected` →
-   `geounselected` →
-   `axisareaselected` →
-   `brush` →
-   `brushEnd` →
-   `brushselected` →
-   `globalcursortaken` →
-   `rendered` →
-   `finished` →
-   Mouse events
    -   `click` →
    -   `dblclick` →
    -   `mouseover` →
    -   `mouseout` →
    -   `mousemove` →
    -   `mousedown` →
    -   `mouseup` →
    -   `globalout` →
    -   `contextmenu` →
-   ZRender events
    -   `zr:click`
    -   `zr:mousedown`
    -   `zr:mouseup`
    -   `zr:mousewheel`
    -   `zr:dblclick`
    -   `zr:contextmenu`

See supported events here →

#### Native DOM Events

As Vue ECharts binds events to the ECharts instance by default, there is some caveat when using native DOM events. You need to prefix the event name with `native:` to bind native DOM events.

<template\>
  <v-chart @native:click\="handleClick" />
</template\>

### Provide / Inject

Vue ECharts provides provide/inject API for `theme`, `init-options`, `update-options` and `loading-options` to help configuring contextual options. eg. for `theme` you can use the provide API like this:

Composition API

import { THEME\_KEY } from "vue-echarts";
import { provide } from "vue";

provide(THEME\_KEY, "dark");

// or provide a ref
const theme \= ref("dark");
provide(THEME\_KEY, theme);

// getter is also supported
provide(THEME\_KEY, () \=> theme.value);

Options API

import { THEME\_KEY } from 'vue-echarts'
import { computed } from 'vue'

export default {
  {
    provide: {
      \[THEME\_KEY\]: 'dark'
    }
  }
}

// Or make injections reactive
export default {
  data() {
    return {
      theme: 'dark'
    }
  },
  provide() {
    return {
      \[THEME\_KEY\]: computed(() \=> this.theme)
    }
  }
}

### Methods

-   `setOption` →
-   `getWidth` →
-   `getHeight` →
-   `getDom` →
-   `getOption` →
-   `resize` →
-   `dispatchAction` →
-   `convertToPixel` →
-   `convertFromPixel` →
-   `containPixel` →
-   `getDataURL` →
-   `getConnectedDataURL` →
-   `clear` →
-   `dispose` →

Note

The following ECharts instance methods aren't exposed because their functionality is already provided by component props:

-   `showLoading` / `hideLoading`: use the `loading` and `loading-options` props instead.
-   `setTheme`: use the `theme` prop instead.

### Slots

Vue ECharts allows you to define ECharts option's `tooltip.formatter` and `toolbox.feature.dataView.optionToContent` callbacks via Vue slots instead of defining them in your `option` object. This simplifies custom HTMLElement rendering using familiar Vue templating.

**Slot Naming Convention**

-   Slot names begin with `tooltip`/`dataView`, followed by hyphen-separated path segments to the target.
-   Each segment corresponds to an `option` property name or an array index (for arrays, use the numeric index).
-   The constructed slot name maps directly to the nested callback it overrides.

**Example mappings**:

-   `tooltip` → `option.tooltip.formatter`
-   `tooltip-baseOption` → `option.baseOption.tooltip.formatter`
-   `tooltip-xAxis-1` → `option.xAxis[1].tooltip.formatter`
-   `tooltip-series-2-data-4` → `option.series[2].data[4].tooltip.formatter`
-   `dataView` → `option.toolbox.feature.dataView.optionToContent`
-   `dataView-media-1-option` → `option.media[1].option.toolbox.feature.dataView.optionToContent`

The slot props correspond to the first parameter of the callback function.

Usage

<template\>
  <v-chart :option\="chartOptions"\>
    <!-- Global \`tooltip.formatter\` \-->
    <template #tooltip\="params"\>
      <div v-for\="(param, i) in params" :key\="i"\>
        <span v-html\="param.marker" />
        <span\>{{ param.seriesName }}</span\>
        <span\>{{ param.value\[0\] }}</span\>
      </div\>
    </template\>

    <!-- Tooltip on xAxis \-->
    <template #tooltip-xAxis\="params"\>
      <div\>X-Axis : {{ params.value }}</div\>
    </template\>

    <!-- Data View Content \-->
    <template #dataView\="option"\>
      <table\>
        <thead\>
          <tr\>
            <th v-for\="(t, i) in option.dataset\[0\].source\[0\]" :key\="i"\>
              {{ t }}
            </th\>
          </tr\>
        </thead\>
        <tbody\>
          <tr v-for\="(row, i) in option.dataset\[0\].source.slice(1)" :key\="i"\>
            <th\>{{ row\[0\] }}</th\>
            <td v-for\="(v, i) in row.slice(1)" :key\="i"\>{{ v }}</td\>
          </tr\>
        </tbody\>
      </table\>
    </template\>
  </v-chart\>
</template\>

Example →

Note

Slots take precedence over the corresponding callback defined in `props.option`.

### Static Methods

Static methods can be accessed from `echarts` itself.

CSP: `style-src` or `style-src-elem`
------------------------------------

If you are **both** enforcing a strict CSP that prevents inline `<style>` injection and targeting browsers that don't support the CSSStyleSheet() constructor, you need to manually include `vue-echarts/style.css`.

Migration to v8
---------------

Note

Please make sure to read the upgrade guide for ECharts 6 as well.

The following breaking changes are introduced in `vue-echarts@8`:

-   **Vue 2 support is dropped:** If you still need to stay on Vue 2, use `vue-echarts@7`.
    
-   **Browser compatibility changes:** We no longer provide compatibility for browsers without native `class` support. If you need to support legacy browsers, you must transpile the code to ES5 yourself.
    
-   **CSP entry point removed:** The entry point `vue-echarts/csp` is removed. Use `vue-echarts` instead. You only need to manually include `vue-echarts/style.css` if you are **both** enforcing a strict CSP that prevents inline `<style>` injection and targeting browsers that don't support the `CSSStyleSheet()` constructor.
    

Local development
-----------------

pnpm i
pnpm dev

Open `http://localhost:5173` to see the demo.

Notice
------

The Apache Software Foundation Apache ECharts, ECharts, Apache, the Apache feather, and the Apache ECharts project logo are either registered trademarks or trademarks of the Apache Software Foundation.
