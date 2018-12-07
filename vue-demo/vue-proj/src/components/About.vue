<template>
<div>
  About{{ their_name }}
</div>
</template>

<script>
/* eslint-disable */
export default {
  name: 'About',
  data() {
      return {
        their_name : this.router.param.name
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bg {
  color : red
}
</style>
