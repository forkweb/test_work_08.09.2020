<template>
<div class="favorites">
  <div class="open-nav">
    <svg class="hamburger-menu" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
      <path fill-rule="evenodd" d="M4,5 L20,5 C20.5522847,5 21,5.44771525 21,6 C21,6.55228475 20.5522847,7 20,7 L4,7 C3.44771525,7 3,6.55228475 3,6 C3,5.44771525 3.44771525,5 4,5 Z M4,17 L20,17 C20.5522847,17 21,17.4477153 21,18 C21,18.5522847 20.5522847,19 20,19 L4,19 C3.44771525,19 3,18.5522847 3,18 C3,17.4477153 3.44771525,17 4,17 Z M4,11 L20,11 C20.5522847,11 21,11.4477153 21,12 C21,12.5522847 20.5522847,13 20,13 L4,13 C3.44771525,13 3,12.5522847 3,12 C3,11.4477153 3.44771525,11 4,11 Z"/>
    </svg>
  </div>
  <div class="nav-bar">

    <nav class="main-nav">

      <svg class="nav-close" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 357 357" xml:space="preserve">
        <g id="close">
          <polygon points="357,35.7 321.3,0 178.5,142.8 35.7,0 0,35.7 142.8,178.5 0,321.3 35.7,357 178.5,214.2 321.3,357 357,321.3 
                    214.2,178.5"/>
        </g>
      </svg>

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
    OpenNav(){
    $('.open-nav').on('click', function() {
      console.log("adas");
      $('.hamburger-menu').toggleClass('animate');
      if ($('.hamburger-menu').hasClass('animate')) {
        $(".nav-bar").css("left", "0");
      } else {
        $(".nav-bar").css("left", "-100%");
      }
    });
    },
    CloseNav(){
      $(".nav-close").on('click',function(){
        $(".nav-bar").css("left", "-100%");
        $(".hamburger-menu").removeClass("animate");
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
    this.OpenNav();
    this.CloseNav();
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
