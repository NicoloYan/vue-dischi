<template>
  <div id="app">
    <PageHeader />
    <AlbumList />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import PageHeader from './components/PageHeader.vue'
import AlbumList from './components/AlbumList.vue'

export default {
  name: 'App',
  components: {
    PageHeader,
    AlbumList
  }
}
</script>

<style lang="scss">
@import '@/assets/scss/style.scss';
</style>
