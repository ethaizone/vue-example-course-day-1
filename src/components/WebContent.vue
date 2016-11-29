<template>
  <div>
    <span v-if="!content">** This is homepage **</span>
    <span v-else>Content is <b>{{ content }}</b></span>
  </div>
</template>

<script>
import bus from './../bus'

var contentData = {
  content: null
}
bus.$on('goto', function (item) {
  contentData.content = item
})

export default {
  name: 'web-content',
  data () {
    return contentData
  }
}
</script>

<style scoped>
div {
  margin-top: 20px;
  border: solid 3px red;
}
</style>
