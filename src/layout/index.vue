<template>
  <div :class="classObj" class="app-wrapper">
    <div class="drawer-bg">layout</div>
    <sidebar class="sidebar-container"/>
    <div class="main-container">
      <div class="fixed-header">
        <navbar />
      </div>
      <app-main />
    </div>
  </div>
</template>

<script>
import { Navbar, Sidebar, AppMain } from './components'

export default {
  name: 'Layout',
  components: {
    Navbar,
    Sidebar,
    AppMain
  },
  computed: {

  }
}
</script>

<style>

</style>
