<template>
<div class="header-wrapper">
    <div class="logo">
        <h1>BOOLFIX</h1>
    </div>
    <div class="search-wrapper" >
        <!-- v-model per salvare nella variabile il testo digitato -->
        <input v-model="searchText" type="text" placeholder="genere..." @key.enter="$emit('ApiRequested', searchText)">
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
//  height: 130px;
 background-color: black;
 padding: 20px;
 display: flex;
 justify-content:space-between ;
 line-height: 50px;
    .logo{
        display: inline-block;
        h1{
            color:red;
            font-size: 20px;
        }
    }
    .search-wrapper{
        line-height: 50px;
        input{
            margin-right:20px;
        }
    }

}
</style>
