<template>
<div class="header-wrapper">
    <div class="logo">
        <h1>BOOLFIX</h1>
    </div>
    <div class="search-wrapper" >
        <!-- v-model per salvare nella variabile il testo digitato -->
        <input v-model="searchText" type="text" placeholder="genere..." @key.enter="$emit('ApiRequested1', searchText)">
        <!-- utilizzo emit per mandare ad app l'attivazione della funzione APIrequest con il testo inserito nella input-->
        <button @click="$emit('ApiRequested', searchText)">Cerca</button>
        
    </div>
    
</div>
</template>

<script>

export default {
  name: "Header",
//   nei data le informazioni contenute nell'input per poi mandarle al main
  data: function(){
      return {
         searchText:'',
         }    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header-wrapper{
 width:100%;
//  height: 200px;
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
    .movies{
        color: aliceblue;
        ul{
            // list-style: none;
            li{
                margin:20 20;
                padding:20px;
                color:red;
            }
        }
    }
}
</style>
