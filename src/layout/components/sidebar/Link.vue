<template>
  <component :is="type">
    <slot />
  </component>
</template>

<script>
import { isExternal } from '@/utils/validate'

export default {
  props: {
    to: {
      type: String,
      require: true
    }
  },
  computed: {
    isExternal () {
      return isExternal(this.to)
    },
    type () {
      if (this.isExternal) {
        return 'a'
      }
      return 'router-link'
    }
  },
  methods: {
    linkProps (to) {
      if (this.isExternal) {
        return {
          href: to,
          target: '_blank',
          rel: 'noopener'
        }
      }
      return {
        to: to
      }
    }
  },
  created () {
    console.log('app link init')
    console.log(this.to)
  }
}
</script>
/**
<a> 标签定义超链接，用于从一张页面链接到另一张页面
也即使说，通过a标签进行跳转，页面会被重新渲染，即相当于重新打开一个新的网页
用href属性指定目标地址，target="_blank"打开新窗口

<router-link>具有路由功能的应用中(点击)导航。
通过 to 属性指定目标地址，默认渲染成带有正确链接的 <a> 标签，可以通过配置 tag 属性生成别的标签.。
通过router-link进行跳转不会跳转到新的页面，也不会重新渲染，它会选择路由所指的组件进行渲染，避免了重复渲染.
 */
