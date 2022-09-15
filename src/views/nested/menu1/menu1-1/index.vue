<template>
  <div>
    <input type="text" v-model="name">
    <p>{{ name }}</p>
    <input type="text" v-model="info.hobby">
    <p>{{ info }}</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      name: 'chitanda',
      info: {
        hobby: 'photography'
      }
    }
  },
  watch: {
    name (newVal, oldVal) {
      console.log('name', newVal, oldVal)
    },
    info: {
      handler (newVal, oldVal) {
        console.log('info', newVal, oldVal)
      },
      deep: true
    }
  }
}
</script>

<style>
</style>
