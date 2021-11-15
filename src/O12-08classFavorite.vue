<template>
  <div>
      <button :class="dataClass">Menu</button>
      <!-- condition -->
      <div class="favoriteContainer">
          {{isFavorite}}
          <button :class="isFavorite?'activeButton':'defaultButton'" @click="toggleFavorite">Favorite</button>
      </div>
      <!-- open/close class with data -->
      <div class="favoriteContainer">
        <button :class="{activeButton: isFavorite}">Menu2</button>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            dataClass:'activeButton',
            isFavorite:false,
        }
    },
    methods:{
        toggleFavorite(){
            this.isFavorite=!this.isFavorite
        }
    }
}
</script>

<style>
.activeButton{
    background-color: crimson;
    color: white;
}
.defaultButton{
    background-color: gray;
}
.favoriteContainer{
    margin-top: 16px;
}
</style>