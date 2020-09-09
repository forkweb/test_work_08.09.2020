<template>
  <div id="app">
    <div class="site">
      <div class="content">
          <ListFilms></ListFilms>
      </div>
    </div>
    
  </div>
</template>

<script>
import ListFilms from './components/ListFilms.vue'

export default {
  name: 'App',
  components: {
    ListFilms
  }
}
</script>

<style lang="scss" type="text/scss">
  @import "./style/main.scss";
  @import "./style/adaptive.scss";
</style>