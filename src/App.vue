<template>
  <div id="app">
    <div class="info">可拖拽组件</div>
    <div class="container">
      <stretch-board></stretch-board>
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
  .container {
    width: 100%;
    position: absolute;
    top: calc(100vh - 200px);
    bottom: 0;
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