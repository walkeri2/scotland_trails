<template lang="html">
  <div v-if='trail' id='trailList'>
    <h2>Trail Details</h2>

    <h3>{{ trail.name }}</h3>
    <img :src="trail.imgMedium" height= 120px />
    <p>Description: {{trail.summary}}</p>
    <p>Difficulty: {{trail.difficulty}}</p>
    <p>Stars: {{trail.stars}}</p>
    <p>Length: {{trail.length}} miles</p>
    <p>Ascent: {{trail.ascent}} feet</p>
    <p>Descent: {{trail.descent}} feet</p>

    <hr>
  </div>

</template>

<script>
import{eventBus} from '../main.js'

export default {
  name: 'trail-detail',
  props: ['trail'],

}
</script>

<style lang="css" scoped>

#trailList {
  align-items: center;
}
</style>
