<template lang="html">
  <div>
    <label>Select a Trail:</label>
      <ul>
        <list-item v-for="(trail, index) in trails" :trail="trail" :key="index"></list-item>
      </ul>
    </div>

</template>

<script>
import ListItem from './TrailItem.vue'

export default {
  name: 'trail-list',
  props: ['trails'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
