<template>

  <div id="app">
    <Header @ApiRequested="APILoad" />
    <Main :searchedMovieList="movieList" :searchedseriesList="seriesList"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from 'axios';
export default {
  
  name: "App",
  components: {
    Header, Main,
  },

  data: function(){
        return {
            movieList: [],
            seriesList:[],
            apiKey:'5df2944e3de5ac0afa350421d515c59b',
            queryValue:'',
        };
    },
    methods:{
      // con questa funzione posso poi aggiungere altre funzioni che richiamo con questa
      // il testo è preso dalla emit del figlio Header
      APILoad: function(searchText){
        this.queryValue = searchText;
        this.APIMovieRequest();
        this.APISeriesRequest();
      },
    APIMovieRequest : function(){
        axios.get('https://api.themoviedb.org/3/search/movie',
        {
            params:{
                api_key: this.apiKey,
                query: this.queryValue,
            }
        })
        .then((response) =>{
            this.movieList = response.data.results;
        });
    },
    APISeriesRequest : function(){
        axios.get('https://api.themoviedb.org/3/search/tv',
        {
            params:{
                api_key: this.apiKey,
                query: this.queryValue,
            }
        })
        .then((response) =>{
            this.seriesList = response.data.results;
        });
    }
  }
};
</script>

<style lang="scss">
@import url('./components/style/general.scss');
#app {
  width: 100%;
    font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
}
</style>
