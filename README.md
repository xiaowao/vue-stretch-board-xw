# vue-dragable-board-xw

一个基于 [vue](https://www.npmjs.com/package/vue) 的可拖拽拉伸面板组件，支持组件的上下高度的动态拉伸及压缩。

## Installing

```shell
npm install vue-dragable-board-xw --save
```

```javascript
import StretchleBoard from 'vue-stretch-board-xw'
```
## 版本链
v1.0.0 基础功能搭建

## Example

```html
<template>
  <div id="app">
    <div class="info">可拖拽组件</div>
    <!--待拉伸的面板容器-->
    <div class="container">
      <!--插件注入-->
      <stretch-board></stretch-board>
      <!--面板内容-->
      <div class="container-body">
        <ul>
          <li style="color: red">favor1: 芒果芝士蛋糕</li>
          <li style="color: pink">favor2: 草莓奶油蛋糕</li>
          <li style="color: orange">favor3: 黑森林yo蛋糕</li>
          <li>favor4: 提拉米苏蛋糕</li>
          <li>favor5: 红丝绒慕斯蛋糕</li>
          <li>favor6: 巧克力布朗尼蛋糕</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
import StretchBoard from './components/StretchBoard'
export default {
  name: 'app',
  components: {
    StretchBoard
  }
}
</script>
<style lang="scss">
body, ul, li {
  margin: 0;
  padding: 0;
}
#app {
  .info {
    width: 100%;
    height: 200px;
    line-height: 200px;
    text-align: center;
    font-size: 36px;
    font-weight: bold;
  }
  .container { // 待拖拽的div
    width: 100%;
    position: absolute;
    top: calc(100vh - 200px); // 初始定位
    bottom: 0; // 纵向拉伸
    border-top: 1px solid #ccc;
    background: #fff;
    z-index: 999;
    &-body {
      width: 100%;
      height: 100%;
      overflow: auto;
      ul {
        padding: 20px 0 20px 50px;
        list-style: none;
        li {
          padding: 5px 0;
        }
      }
    }
  }
}
</style>
```
## Options

### Props

<thead>
    <tr>
      <th>name</th>
      <th>type</th>
      <th>default</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>top</td>
      <td>Number</td>
      <td>100</td>
      <td>纵向可拉伸的最高位置（距顶部）</td>
    </tr>
    <tr>
      <td>bottom</td>
      <td>Number</td>
      <td>1000 * 1000</td>
      <td>纵向可压缩的最小位置（距底部）</td>
    </tr>
  </tbody>
</table>
