<template>

  <div id="app">
    
    <Header @ApiRequested="APILoad"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import axios from 'axios';
export default {
  
  name: "App",
  components: {
    Header,
  },
  data: function(){
        return {
            movieList: [],
            apiKey:'5df2944e3de5ac0afa350421d515c59b',
            queryValue:'',
        };
    },
    methods:{
      // con questa funzione posso poi aggiungere altre funzioni che richiamo con questa
      // il testo è preso dalla emit del figlio Header
      APILoad: function(searchText){
        this.queryValue = searchText;
        this.APIrequest();
      },
    APIrequest : function(){
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
    }
  }
};
</script>

<style lang="scss">
@import url('./components/style/general.scss');
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100%;
  
}
</style>
