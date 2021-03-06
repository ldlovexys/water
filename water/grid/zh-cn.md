# 栅格系统

## 24栅格系统
<w-row type="flex" justify="center" align="middle" className="demo-row" class="demo-first">
  <w-col :span="24" className="demo-col" class="demo-text">100%</w-col>
</w-row>
<w-row type="flex" justify="center" align="middle" className="demo-row">
  <w-col :span="12" v-for="(a, aIndex) in 2" :key="aIndex" className="demo-col" class="demo-text">50%</w-col>
</w-row>
<w-row type="flex" justify="center" align="middle" className="demo-row">
  <w-col :span="8" v-for="(a, aIndex) in 3" :key="aIndex" className="demo-col" class="demo-text">33.33%</w-col>
</w-row>

在多数业务情况下，Ant Design需要在设计区域内解决大量信息收纳的问题，因此在 12 栅格系统的基础上，我们将整个设计建议区域按照 24 等分的原则进行划分。

划分之后的信息区块我们称之为『盒子』。建议横向排列的盒子数量最多四个，最少一个。『盒子』在整个屏幕上占比见上图。设计部分基于盒子的单位定制盒子内部的排版规则，以保证视觉层面的舒适感。

## 概述

布局的栅格化系统，我们是基于行（ row ）和列（ col ）来定义信息区块的外部框架，以保证页面的每个区域能够稳健地排布起来。下面简单介绍一下它的工作原理：

- 通过row在水平方向建立一组 column（简写 col ）
- 你的内容应当放置于 col 内，并且，只有 col 可以作为 row 的直接元素
- 栅格系统中的列是指 1 到 24 的值来表示其跨越的范围。例如，三个等宽的列可以使用 .col-8 来创建
- 如果一个 row 中的 col 总和超过 24，那么多余的 col 会作为一个整体另起一行排列

## Flex 布局

我们的栅格化系统支持 Flex 布局，允许子元素在父节点内的水平对齐方式 - 居左、居中、居右、等宽排列、分散排列。子元素与子元素之间，支持顶部对齐、垂直居中对齐、底部对齐的方式。同时，支持使用 order 来定义元素的排列顺序。

Flex 布局是基于 24 栅格来定义每一个『盒子』的宽度，但排版则不拘泥于栅格。

## 基本栅格

***output***
<w-row className="demo-row" class="demo-second">
  <w-col :span="8" className="demo-col">
    <div class="demo-text">col-8</div>
  </w-col>
  <w-col :span="8" className="demo-col">
    <div class="demo-text">col-8</div>
  </w-col>
  <w-col :span="8" className="demo-col">
    <div class="demo-text">col-8</div>
  </w-col>
</w-row>
<w-row className="demo-row">
  <w-col :span="6" className="demo-col">
    <div class="demo-text">col-6</div>
  </w-col>
  <w-col :span="6" className="demo-col">
    <div class="demo-text">col-6</div>
  </w-col>
  <w-col :span="6" className="demo-col">
    <div class="demo-text">col-6</div>
  </w-col>
  <w-col :span="6" className="demo-col">
    <div class="demo-text">col-6</div>
  </w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" class="demo-second">
  <w-col :span="8" className="demo-col">
    <div class="demo-text">col-8</div>
  </w-col>
  <w-col :span="8" className="demo-col">
    <div class="demo-text">col-8</div>
  </w-col>
  <w-col :span="8" className="demo-col">
    <div class="demo-text">col-8</div>
  </w-col>
</w-row>
<w-row className="demo-row">
  <w-col :span="6" className="demo-col">
    <div class="demo-text">col-6</div>
  </w-col>
  <w-col :span="6" className="demo-col">
    <div class="demo-text">col-6</div>
  </w-col>
  <w-col :span="6" className="demo-col">
    <div class="demo-text">col-6</div>
  </w-col>
  <w-col :span="6" className="demo-col">
    <div class="demo-text">col-6</div>
  </w-col>
</w-row>
```

## 间隔用法

***output***

<w-row :gutter="16" className="demo-row" class="demo-second">
  <w-col :span="6" className="demo-col" class="demo-text">col-6</w-col>
  <w-col :span="6" className="demo-col" class="demo-text">col-6</w-col>
  <w-col :span="6" className="demo-col" class="demo-text">col-6</w-col>
  <w-col :span="6" className="demo-col" class="demo-text">col-6</w-col>
</w-row>

***input***

``` vue
<w-row :gutter="16" className="demo-row" class="demo-second">
  <w-col :span="6" className="demo-col" class="demo-text">col-6</w-col>
  <w-col :span="6" className="demo-col" class="demo-text">col-6</w-col>
  <w-col :span="6" className="demo-col" class="demo-text">col-6</w-col>
  <w-col :span="6" className="demo-col" class="demo-text">col-6</w-col>
</w-row>
```

## 栅格顺序

***output***

<w-row className="demo-row" type="flex" class="demo-second">
  <w-col :span="6" className="demo-col" :order="4" class="demo-text">1 | order-4</w-col>
  <w-col :span="6" className="demo-col" :order="3" class="demo-text">2 | order-3</w-col>
  <w-col :span="6" className="demo-col" :order="2" class="demo-text">3 | order-4</w-col>
  <w-col :span="6" className="demo-col" :order="1" class="demo-text">4 | order-1</w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" type="flex" class="demo-second">
  <w-col :span="6" className="demo-col" :order="4" class="demo-text">1 | order-4</w-col>
  <w-col :span="6" className="demo-col" :order="3" class="demo-text">2 | order-3</w-col>
  <w-col :span="6" className="demo-col" :order="2" class="demo-text">3 | order-4</w-col>
  <w-col :span="6" className="demo-col" :order="1" class="demo-text">4 | order-1</w-col>
</w-row>
```

## 栅格排序

***output***

<w-row className="demo-row" class="demo-second">
  <w-col :span="18" :pull="6" className="demo-col" class="demo-text">col-18 | pull-6</w-col>
  <w-col :span="6" :push="18" className="demo-col" class="demo-text">col-6 | push-18</w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" class="demo-second">
  <w-col :span="18" :pull="6" className="demo-col" class="demo-text">col-18 | pull-6</w-col>
  <w-col :span="6" :push="18" className="demo-col" class="demo-text">col-6 | push-18</w-col>
</w-row>
```

## 栅格偏移

***output***

<w-row className="demo-row" class="demo-second">
  <w-col :span="8" className="demo-col" class="demo-text">col-8</w-col>
  <w-col :span="8" className="demo-col" :offset="8" class="demo-text">col-8 | offset-8</w-col>
</w-row>
<br>
<w-row className="demo-row">
  <w-col :span="6" className="demo-col" :offset="8" class="demo-text">col-6 | offset-8</w-col>
  <w-col :span="6" className="demo-col" :offset="4" class="demo-text">col-6 | offset-4</w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" class="demo-second">
  <w-col :span="8" className="demo-col" class="demo-text">col-8</w-col>
  <w-col :span="8" className="demo-col" :offset="8" class="demo-text">col-8 | offset-8</w-col>
</w-row>
<br>
<w-row className="demo-row">
  <w-col :span="6" className="demo-col" :offset="8" class="demo-text">col-6 | offset-8</w-col>
  <w-col :span="6" className="demo-col" :offset="4" class="demo-text">col-6 | offset-4</w-col>
</w-row>
```

## 栅格排列 子元素向左排列

***output***

<w-row className="demo-row" type="flex" justify="start" align="top" class="demo-second">
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" type="flex" justify="start" align="top" class="demo-second">
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
</w-row>
```

## 顶部对齐

***output***

<w-row className="demo-row" type="flex" justify="center" align="top" class="demo-second">
  <w-col :span="4" className="demo-col" class="demo-text">col-4 </w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4 </w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4 </w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4 </w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" type="flex" justify="center" align="top" class="demo-second">
  <w-col :span="4" className="demo-col" class="demo-text">col-4 </w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4 </w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4 </w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4 </w-col>
</w-row>
```

## 底部对齐

***output***

<w-row className="demo-row" type="flex" justify="center" align="bottom" class="demo-second">
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" type="flex" justify="center" align="bottom" class="demo-second">
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
  <w-col :span="4" className="demo-col" class="demo-text">col-4</w-col>
</w-row>
```

## 栅格响应式

***output***

<w-row className="demo-row" class="demo-second">
  <w-col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
  <w-col :xs="{ span: 11, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
  <w-col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" class="demo-second">
  <w-col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
  <w-col :xs="{ span: 11, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
  <w-col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
</w-row>
```

## 栅格其他属性

***output***

<w-row className="demo-row" class="demo-second">
  <w-col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
  <w-col :xs="{ span: 11, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
  <w-col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
</w-row>

***input***

``` vue
<w-row className="demo-row" class="demo-second">
  <w-col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
  <w-col :xs="{ span: 11, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
  <w-col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }" className="demo-col" class="demo-text">w-col</w-col>
</w-row>
```

## API

### w-row 属性

|属性|说明|类型|是否必须|默认|
|---|---|----|-------|---|
|gutter|栅格间距，单位 px ，左右平分。范围： 0 ~ 48 |Number|否|0|
|basin|垂直栅格间距，单位 px ，上下平分。范围： 0 ~ 48 |Number|否|0|
|type|布局模式，可选值为 flex 或不选。 flex 在现代浏览器下有效。|String|否|无|
|align|flex 布局下的垂直对齐方式，可选值为 top 、 middle 、 bottom 。|String|否|无|
|justify|flex 布局下的水平排列方式，可选值为 start 、 end、center 、 space-around、 space-between 。|String|否|无|
|className|自定义的 class 名称。会在最后追加。|String \| Object|否|无|
|tag|自定义的 标签 名称。|String|否|div|
|prefix|自定义的 class 的前缀名称。在最后追加，但在 className 之前。|String|否|无|

### w-col 属性

|属性|说明|类型|是否必须|默认|
|---|---|----|-------|---|
|span|栅格的占位格数，可选值为 0 ~ 24 的整数，为 0 时，相当于 display: none|Number|否|无|
|tag|自定义标签名字|String|否|div|
|offset|栅格左侧的间隔格数，间隔内不可以有栅格|Number|否|无|
|push|栅格向右移动格数|Number|否|无|
|pull|栅格向左移动格数|Number|否|无|
|order|定义元素的排列顺序|Number|否|无|
|className|自定义的 class 名称。会在最后追加。|String \| Object|否|无|
|prefix|自定义的 class 的前缀名称。在最后追加，但在 className 之前。|String|否|无|
xs|>= 576px 响应式栅格，可为栅格数或一个包含其他属性的对象|	Number \| Object|否|无|
sm|≥ 576px 响应式栅格，可为栅格数或一个包含其他属性的对象|	Number \| Object|否|无|
md|≥ 768px 响应式栅格，可为栅格数或一个包含其他属性的对象|	Number \| Object|否|无|
lg|≥ 992px 响应式栅格，可为栅格数或一个包含其他属性的对象|	Number \| Object|否|无|
xl|≥ 1200px 响应式栅格，可为栅格数或一个包含其他属性的对象|	Number \| Object|否|无|
xxl|≥ 1600px 响应式栅格，可为栅格数或一个包含其他属性的对象|	Number \| Object|否|无|

<script>
import { WCol, WRow } from './index';

export default {
  components: {
    WCol,
    WRow,
  },
};
</script>

<style lang="scss">
@import './style/col.scss';
@import './style/row.scss';

.demo {
  &-first {
    margin-top: 24px !important;
  }

  &-second {
    margin-top: 16px !important;
  }

  &-row {
    margin-bottom: 8px;
    background-image: linear-gradient(90deg,#f5f5f5 4.16666667%,transparent 0,transparent 8.33333333%,#f5f5f5 0,#f5f5f5 12.5%,transparent 0,transparent 16.66666667%,#f5f5f5 0,#f5f5f5 20.83333333%,transparent 0,transparent 25%,#f5f5f5 0,#f5f5f5 29.16666667%,transparent 0,transparent 33.33333333%,#f5f5f5 0,#f5f5f5 37.5%,transparent 0,transparent 41.66666667%,#f5f5f5 0,#f5f5f5 45.83333333%,transparent 0,transparent 50%,#f5f5f5 0,#f5f5f5 54.16666667%,transparent 0,transparent 58.33333333%,#f5f5f5 0,#f5f5f5 62.5%,transparent 0,transparent 66.66666667%,#f5f5f5 0,#f5f5f5 70.83333333%,transparent 0,transparent 75%,#f5f5f5 0,#f5f5f5 79.16666667%,transparent 0,transparent 83.33333333%,#f5f5f5 0,#f5f5f5 87.5%,transparent 0,transparent 91.66666667%,#f5f5f5 0,#f5f5f5 95.83333333%,transparent 0);
  }

  &-col {
    color: #333;

    &:nth-of-type(odd) {
      color: #fff;
      background: rgba(25, 150, 249, 0.5);
    }
  }

  &-text {
    padding: 30px 0;
    text-align: center;
    font-size: 30px;
    line-height: 1;
  }
}
</style>
