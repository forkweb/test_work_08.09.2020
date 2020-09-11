<template>
<div class="favorites">
  <div class="nav-bar">
    
    <nav class="main-nav">
      <ul class="cd-accordion-menu animated">
        <li class="has-children">
          <!-- <input type="checkbox" name ="group-1" id="group-1" checked> -->
          <input type="checkbox" name ="group-1" id="group-1">
          <label for="group-1">Действия</label>

              <ul>
                <li><a href="">Просмотры</a></li>
                <li><a href="">Избранное</a></li>
                <li><a href="">Отложенное</a></li>
              </ul>
        </li>

        <li class="has-children">
          <input type="checkbox" name ="group-2" id="group-2">
          <label for="group-2">Тарифы</label>

          <ul>
            <li><a href="">Максимальный</a></li>
            <li><a href="">Средний</a></li>
            <li><a href="">Минимальный</a></li>
          </ul>
        </li>


        <li class="has-children">
          <a href="">Настройки</a>
        </li>
      </ul>
    </nav>

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
