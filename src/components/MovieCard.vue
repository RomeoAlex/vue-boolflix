<template>

    <div class="movie-container">
        <div class="poster">
            <div class="poster-box">
                <div v-if="details.poster_path === null" class="not-found">
                    <h2>IMMAGINE NON TROVATA</h2>
                    <h2>Descrizione all'interno</h2>
                    <img :src="require(`../assets/error-404.jpg`)" alt="">
                </div>
                <div v-else>
                    <img :src="'https://image.tmdb.org/t/p/w300' + details.poster_path" :alt="details.title">
                </div>
            </div>
        </div>
        
        <div class="description-box">
                <div class="description">
                    <div class="title">
                        <span>Titolo : {{details.title ? details.title : details.name }}</span>   
                    </div>
                    <div class="title original">
                        <span>Titolo Originale : {{details.original_title ? details.original_title : details.original_name}}</span>
                    </div>
                    <div class="language">
                        <span>Lingua Originale : </span> 
                        <span v-if="flagsArray.includes(details.original_language)">
                            <img :src="require(`./nation-flags/${details.original_language}.png`)" alt="">
                        </span>
                        <span v-else>
                            {{details.original_language}}
                        </span>
                    </div>
                    <div class="vote">
                        <span>Voto : {{details.vote_average}}</span>
                    </div>
                    <div class="overview">
                        <p>
                            Trama:{{details.overview}}
                        </p>
                    </div>
                </div>
        </div>
            
        
    </div>
    
 
</template>
<script>

export default {
    name:'MovieCard',
    data:function(){
        return{
            flagsArray:['it','en']
        }  
    },
    props: {
        details: Object
    } 
}
</script>

<style lang="scss" scoped>

    .movie-container{
        margin-top:20px;
        width: calc((100% / 5) - 15px);
        min-height: 500px;
        padding: 30px;
        
        margin-bottom: 20px;
        margin-right:15px;
        position: relative;
        .poster{
            
            background-color: #2e3a46;
            position: absolute;
            top: 0;
            left: 0;
            display: block;
            width: 340px;
            height: 480px;
            z-index: 2;
            .poster-box{
                padding:10px;
                .not-found{
                    img{
                    width:300px;
                    }
                        }
                    img{
                    padding:10px;    
                    }
            }
            
        }
        
        .description-box{
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
            width: 340px;
            height: 480px;
            background-color: #2e3a46;
            
            .description{
                font-size:15px;
                padding:15px;
                color: white;
                 
            .title{  
                font-size:20px;
            
              
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
                height:40px;
                width:50px;
            }
        }
        .vote{
            font-size: 20px;
            color:brown;
            span{
                font-weight: bold;
            }
        }
        .overview p{
            max-height:300px;
            overflow-y: scroll;
        }
        .overview p::-webkit-scrollbar{
           width: 10px; 
        }
        }
        }

    }
            .movie-container:hover .poster{
            display: none;
                        }

</style>