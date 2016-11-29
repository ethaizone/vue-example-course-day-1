<template>
  <div>
    <input placeholder="Type keyword in me!" v-model="keyword">
    <button v-show="keyword" @click="search">Search</button>
  </div>
</template>

<script>
import bus from './../bus'

var contentData = {
  content: 'homepage'
}
bus.$on('goto', function (item) {
  contentData.content = item
})

export default {
  name: 'search-box',
  data () {
    return {
      keyword: null
    }
  },
  methods: {
    search () {
      window.alert('You search ' + this.keyword)
      this.keyword = null
    }
  }
}
</script>

<style scoped>
div {
  margin-top: 20px;
  border: solid 3px green;
}
</style>
