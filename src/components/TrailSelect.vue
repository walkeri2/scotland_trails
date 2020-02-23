<template lang="html">
  <form>
    <label for="trailSelect">Select A Trail: </label>
    <select id="trailSelect" v-on:change="handleChange" v-model="trail">
      <option v-for="(trail, index) in trails" :value="trail" :key="index">{{trail.name}}</option>
   </select>
  </form>
</template>

<script>
import ListItem from './TrailItem.vue';
import{eventBus} from '../main.js'

export default {
  name: 'trail-select',
  data(){
    return {
      trail: null
    }
  },
  props: ['trails'],
  methods: {
    handleChange() {
      eventBus.$emit('selected-trail', this.trail);
    }
  }
}
</script>
<style lang="css" scoped>
</style>
