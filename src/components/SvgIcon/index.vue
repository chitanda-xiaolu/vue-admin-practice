<template>
  <div v-if="isExternal"/>
</template>

<script>
import { isExternal } from 'util/validate';

export default {
  name: 'SvgIcon',
  props: {
    iconClass: {
      type: String,
      required: true
    },
    classNmae: {
      type: String,
      default: ''
    }
  },
  computed: {
    isExternal () {
      return isExternal(this.iconClass)
    },
    iconName () {
      return `#icon-${this.iconClass}`
    },
    svgClass () {
      if (this.className) {
        return 'svg-icon ' + this.className
      } else {
        return 'svg-icon'
      }
    },
    styleExternalIcon () {
      return {
        mask: `url(${this.iconClass}) no-repeat 50% 50%`,
        '-webkit-mask': `url(${this.iconClass}) no-repeat 50% 50%`
      }
    }
  }
}
</script>

<style>

</style>