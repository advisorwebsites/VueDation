<template>
  <ul class="accordion" data-accordion>
    <slot></slot>
  </ul>
</template>

<script>
import coerceBoolean from './utils/coerceBoolean.js'
import AccordionItem from './AccordionItem.vue'
  export default {
    props: {
      multiExpand: {
        type: Boolean,
        coerce: coerceBoolean,
        default: false
      },
      allowAllClosed: {
        type: Boolean,
        coerce: coerceBoolean,
        default: false
      }
    },
    created() {
    }
  }
</script>
