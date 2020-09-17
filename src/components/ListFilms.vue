<template>
<div class="favorites">
  <div class="nav-bar">

    <nav class="main-nav">

      <ul class="cd-accordion-menu animated">
        <li class="has-children">
          <input type="checkbox" name ="group-1" id="group-1" checked>
          <label class="title_menu_drop active_slide_menu" for="group-1">Действия</label>
          <ul>
            <li class="drop_data"><a href="#0">Просмотры</a></li>
            <li class="drop_data drop_data_active"><a href="#0">Избранное</a></li>
            <li class="drop_data"><a href="#0">Отложенное</a></li>
          </ul>
        </li>

        <li class="has-children">
          <input type="checkbox" name ="group-2" id="group-2">
          <label class="title_menu_drop" for="group-2">Тарифы</label>

          <ul>
            <li class="drop_data"><a href="#0">Максимальный</a></li>
            <li class="drop_data"><a href="#0">Средний</a></li>
            <li class="drop_data"><a href="#0">Минимальный</a></li>
          </ul>
        </li>

        <li class="has-children">
          <a class="drop_data title_menu_drop" href="#0">Настрйоки</a>
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
import $ from "jquery";

export default {
  name: 'ListFilms',
  components: {
    ItemFilms
  },
  watch: {
  },
  methods: {
    Menu() {
      $(document).ready(function(){
        var accordionsMenu = $('.cd-accordion-menu');

        if( accordionsMenu.length > 0 ) {
          
          accordionsMenu.each(function(){
            var accordion = $(this);
            //detect change in the input[type="checkbox"] value
            accordion.on('change', 'input[type="checkbox"]', function(){
              var checkbox = $(this);
              var label = $(this).parent(".has-children").find(".title_menu_drop");
              console.log(checkbox.prop('checked'));
              ( checkbox.prop('checked') ) ? checkbox.siblings('ul').attr('style', 'display:none;').slideDown(300) : checkbox.siblings('ul').attr('style', 'display:block;').slideUp(300);
              ( checkbox.prop('checked') ) ? label.addClass('active_slide_menu') : label.removeClass("active_slide_menu");
            });
          });
        }
      });
    },
    addFavorites(){
      $(document).on("click",".favorites-heart",function(){
        $(this).css("fill","red");
        $(this).css("stroke","red");
      });
    }
  },
  create(){
    
  },
  mounted() {
    this.Menu();
    this.addFavorites();
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
