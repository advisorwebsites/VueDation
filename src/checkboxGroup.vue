<template>
  <div class="button-group" :class="{
    'tiny':sizing == 'tiny',
    'small':sizing == 'small',
    'large':sizing == 'large'
  }">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    props: {
      value: {
        type: Array,
        default() {
          return []
        }
      },
      type: {
        type: String,
        default: 'default'
      },
      sizing: {
        type: String,
        default: ''
      }
    }
  }
</script>
