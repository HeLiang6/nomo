<template>
  <div class="BaiduMap" />
</template>

<script>
export default {
  name: 'Home',
  methods: {
    map: function() {
      map = new Map()
    }
  }
}
</script>

<style lang="scss" scoped>
.BaiduMap{
  width: 100%;
  height: 100%;
}
</style>
