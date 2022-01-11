<template>
<div class="header-wrapper">
    <div class="logo">
        <h1>BOOLFIX</h1>
    </div>
    <div class="search-wrapper">
        <input type="text">
        <button @click="APIrequest">Cerca</button>
    </div>
</div>
</template>

<script>
import axios from 'axios';
export default {
  name: "Header",
  
  methods:{
    APIrequest : function(){
        axios.get('https://api.themoviedb.org/3/search/movie',
        {
            params:{
                api_key:'5df2944e3de5ac0afa350421d515c59b',
                query: 'vita',
            }
        })
        .then((response) =>{
            console.log(response.data.results);
        });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header-wrapper{
 width:100%;
 height: 200px;
 background-color: black;
 padding: 20px 20px;
    .logo{
        display: inline-block;
        h1{
            color:red;
            font-size: 20px;
        }
    }
    .search-wrapper{
        float:right;
        margin: 20px 20px;
    }
}
</style>
