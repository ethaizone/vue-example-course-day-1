<template>
  <div>
    <ul>
      <li v-for="(item, index) in items" 
      v-on:click="selectMe(index, item)"
      v-bind:class="{active: (index == currentSelect)}">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
import bus from './../bus'

export default {
  name: 'sidebar',
  props: ['items'],
  data () {
    return {
      currentSelect: null
    }
  },
  methods: {
    selectMe (index, item) {
      this.currentSelect = index
      bus.$emit('goto', item)
    }
  }
}

</script>

<style scoped>
div {
  border: solid 3px blue;
}
li.active {
  border: dashed 1px black;
}
</style>