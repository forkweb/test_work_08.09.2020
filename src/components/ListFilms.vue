<template>
<div class="favorites">
  <div class="nav-bar">
    Меню
    <p>asdsa</p>
    <p>asdsa</p>
    <p>asdsa</p>
    <p>asdsa</p>
    <p>asdsa</p>
    <p>asdsa</p>
    <p>asdsa</p>
  </div>
  <div class="container">
    <div class="title">Избранное</div>

    <div class="favorites-list">

      <ItemFilms></ItemFilms>

    </div>

  </div>
</div>
</template>

<script>
import ItemFilms from '../components/ItemFilms.vue'

export default {
  name: 'ListFilms',
  components: {
    ItemFilms
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
