<template>
  <div id="vue-stretch-board-xw" v-stretch="value"></div>
</template>
<script>
export default {
  name: 'StretchBoard',
  directives: {
    stretch: {
      bind: function(el, binding, vnode) {
        el.onmousedown = function(e) {
          const parent = el.parentNode
          const disy = e.clientY - parent.offsetTop
          const minTop = binding.value.top
          const maxTop = window.innerHeight - binding.value.bottom
          el.style.top = '-100px'
          el.style.height = '130px'
          document.onmousemove = function(e) {
            let top = e.clientY - disy
            if (!top || top < 0) {
              return
            }
            if (top <= minTop) {
              top = minTop
            } else if (top >= maxTop) {
              top = maxTop
            }
            parent.style.top = top + 'px'
          }
          document.onmouseup = function() {
            document.onmousemove = document.onmouseup = null
            el.style.top = '-1px'
            el.style.height = '3px'
          }
        }
      }
    }
  },
  props: {
    top: {
      type: Number,
      default: 100
    },
    bottom: {
      type: Number,
      default: 150
    }
  },
  computed: {
    value() {
      return {
        top: this.top,
        bottom: this.bottom
      }
    }
  }
}
</script>

<style lang="scss" scoped>
#vue-stretch-board-xw {
  position: absolute;
  top: -1px;
  width: 100%;
  height: 3px;
  background: none;
  cursor: s-resize;
  z-index: 1000;
}
</style>
