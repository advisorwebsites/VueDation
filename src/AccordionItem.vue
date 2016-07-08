<template>
  <li class="accordion-item is-active" data-accordion-item>
    <slot name="accordion-title" class="accordion-title"></slot>
    <slot name="accordion-content" class="accordion-content"  data-tab-content></slot>
  </li>
</template>

<script>
import coerceBoolean from './utils/coerceBoolean.js'

  export default {
    created() {
      
    }
  }
</script>