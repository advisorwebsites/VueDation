<template>
  <div
    v-show="show"
    v-bind:class="{
      'callout':		true,
      'primary':(type == 'primary'),
      'secondary':(type == 'secondary'),
      'success':	(type == 'success'),
      'warning':	(type == 'warning'),
      'alert':	(type == 'alert'),
      'small': (size == 'small'),
      'large': (size == 'large')
    }"
    transition="fade"
    v-bind:style="{width:width}"
    role="alert">
    <button v-show="closable" type="button" class="close"
      @click="show = false">
      <span>&times;</span>
    </button>
    <slot></slot>
  </div>
</template>

<script>
import coerceBoolean from './utils/coerceBoolean.js'

  export default {
    props: {
      type: {
        type: String
      },
      show: {
        type: Boolean,
        coerce: coerceBoolean,
        default: true,
        twoWay: true
      },
      duration: {
        type: Number,
        default: 0
      },
      width: {
        type: String
      },
      size: {
        type: String
      }
    },
    watch: {
      show(val) {
        if (this._timeout) clearTimeout(this._timeout)
        if (val && Boolean(this.duration)) {
          this._timeout = setTimeout(()=> this.show = false, this.duration)
        }
      }
    }
  }
</script>

<style>
.fade-transition {
  transition: opacity .3s ease;
}
.fade-enter,
.fade-leave {
  height: 0;
  opacity: 0;
}
</style>
