<template lang="html">
  <li v-on:click="handleClick">{{trail.name}}</li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'list-item',
  props: ['trail'],
  methods: {
    handleClick(){
      eventBus.$emit('selected-trail', this.trail)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
