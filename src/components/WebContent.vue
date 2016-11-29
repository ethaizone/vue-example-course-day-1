<template>
  <div>
    Content is {{ content }}
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
