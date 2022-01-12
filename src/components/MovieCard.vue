<template>
    <div class="movie-container">
        <img :src="'https://image.tmdb.org/t/p/w300' + details.poster_path" :alt="details.title">
        <div class="title">
             <span>Titolo : </span>   {{details.title}}
            </div>
            <div class="title original">
                <span>Titolo Originale : </span>{{details.original_title}}
            </div>
            <div class="language">
               <span>Lingua Originale : </span> <img :src="'./nation-flags/' + details.original_language + '.png'" alt="">
            </div>
            <div class="vote">
                <span>Voto : </span>{{details.vote_average}}
            </div>
    </div>
    
</template>
<script>

export default {
    name:'MovieCard',
    props: {
        details: Object
    }
}
</script>

<style lang="scss" scoped>


.movie-container{
    width: calc((100% / 5) - 15px);
    min-height: 400px;
    background-color: #2e3a46;
    padding: 30px;
    text-align: center;
    margin-bottom: 20px;
    margin-right:15px;
    .title{  
        margin-top:15px;
        font-size:20px;
        color: white;   
        span{
            font-weight: bold;
        }
    }
    .original{}
    .language{
        margin-top:20px;
        font-size: 20px;
        color:khaki;
        span{
            font-weight: bold;
        }
        img{
            height:100px;
            width:100px;
        }
    }
    .vote{
        font-size: 20px;
        color:brown;
        span{
            font-weight: bold;
        }
    }
}
</style>