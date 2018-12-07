<template>
  <div id="app">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>

    <router-view />
  </div>
</template>

<script>
/* eslint-disable */

export default {
  name: 'app',
  components: {
    Home
  }
}
</script>


<style lang = "sass">
@import '../node_modules/bulma/bulma.sass'
</style>
