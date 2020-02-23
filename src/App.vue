<template>
  <div id="app">
    <h1> Scotland Walks </h1>
    <div class="main-container">
      <trail-select :trails='trails'></trail-select>
      <trail-detail :trail='selectedTrail'></trail-detail>
    </div>
  </div>
</template>

<script>
import TrailList from './components/TrailList.vue';
import TrailSelect from './components/TrailSelect.vue';
import { eventBus } from './main.js';
import TrailItem from './components/TrailItem.vue';
import TrailDetail from './components/TrailDetail.vue';

export default {
  name: 'App',
  data(){
    return {
      trails: [],
      selectedTrail: null
    };
  },
  mounted(){
    fetch('https://www.hikingproject.com/data/get-trails?lat=56.8198&lon=-5.1052&maxDistance=200&maxResults=100&key=200690005-4ce565fde2b3431d0b7b6f90cb2e272e')
    .then(res => res.json())
    .then(data => this.trails = data.trails)


    eventBus.$on('selected-trail', (trail) => {this.selectedTrail = trail})
  },

  components: {
    "trail-list": TrailList,
    "trail-detail": TrailDetail,
    "trail-select": TrailSelect
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
