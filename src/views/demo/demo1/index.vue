<template>
  <div>
    <h1>v-if</h1>
    <p v-if="data === 'a'">a{v-if}</p>
    <p v-else-if="data === 'b'">b{v-if}</p>
    <p v-else>other{v-if}</p>
    <h1>v-show</h1>
    <p v-show="data === 'a'">a{v-show}</p>
    <p v-show="data === 'b'">b{v-show}</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      data: 'b'
    }
  }
}
</script>

<style>

</style>
