<template>
  <div id="app">
    <PageHeader @changeGenre="setGenre"/>
    <AlbumList :selectedGenre="selectedOption"/>
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
  },

  data() {
    return {
      selectedOption: ''
    }
  },

  methods: {
    setGenre(selectedOption) {
      this.selectedOption = selectedOption;
    }
  }
}
</script>

<style lang="scss">
@import '@/assets/scss/style.scss';
</style>
