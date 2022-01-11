<template>
<div class="header-wrapper">
    <div class="logo">
        <h1>BOOLFIX</h1>
    </div>
    <div class="search-wrapper">
        <input type="text">
        <button>Cerca</button>
    </div>
</div>
</template>

<script>
export default {
  name: "Header",
  
};
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
