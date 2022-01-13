<template>
<div class="main-wrapper">
  <div class="title-section">
    <h2>Film</h2>
  </div>
  
      <div class="sub-wrapper">
          
            <MovieCard v-for="(movie, index) in searchedMovieList" :key="index" :details="movie" />
      </div>
      <div class="title-section">
        <h2>Serie-TV</h2> 
      </div> 
  
      <div class="sub-wrapper">      
           
            <MovieCard v-for="(serie, index) in searchedseriesList" :key="index" :details="serie" />
      </div>      
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
        searchedMovieList: Array,
        searchedseriesList: Array
  },
  
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.main-wrapper{
      .title-section{
        background-color: #2e3a46;
      }
      width:100%;
      h2{
        color: aliceblue;
        padding: 30px;
      }
      .sub-wrapper{
      background-color: #2c3e50;
      width: 100%;
      margin: auto;
      display: flex;
      flex-wrap: wrap;
      }
}
</style>
