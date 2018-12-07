<template>
<div>
  <form @submit.prevent="addSkill">
    <input  placeholder="Enter a skill " type="text" v-model="skill"/>

    <input type="checkbox" id = "checkbox" v-model="checked"/>
  </form>
  <ul>
    <li v-for="(data ,index) in skills" :key="index" v-bind:class="{'bg':!bg}" >
     {{ data.skill }}
    </li>
  </ul>
</div>
</template>

<script>
/* eslint-disable */
export default {
  name: 'Skills',
  data() {
      return {
        bg: 'red',
        checked : true,
        skill : '',
        skills : [
          {"skill" : "Vue.js"},
          {"skill" : "Frontend Developer"}
        ]
      }
  },
  props: {
    msg: String
  },
  methods: {
    addSkill() {
      // console.log('add skill.');
      this.skills.push({"skill" : this.skill})
      this.skill = '';
      console.log('add skill .=='+this.checked);
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
