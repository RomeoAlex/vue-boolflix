<template>
  <div class="main-wrapper">
        <MovieCard v-for="(movie, index) in searchedMovieList" :key="index" :details="movie" />
     </div>      
    
  
</template>

<script>
import MovieCard from "./MovieCard.vue";
export default {
  name: "Main",
  components: {
    MovieCard,
  },
  props: {
        searchedMovieList: Array
  },
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.main-wrapper{
background-color: #2c3e50;
width: 100%;
margin: auto;
display: flex;
flex-wrap: wrap;
}

</style>
