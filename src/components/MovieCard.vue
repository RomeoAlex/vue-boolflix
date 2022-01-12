<template>
<div class="movies-wrapper">
    <div class="movies">
        <ul v-for="(movie, index) in movieList" :key="index" :details="movie">
            <li >
                Titolo:{{movie.title}}
                Titolo Originale:{{movie.original_title}}
                Lingua d'origine:{{movie.original_language}}
                Voto:{{movie.vote_average}}
            </li>
          <li>
              Titolo Originale:{{movie.original_title}}
          </li>
        </ul>
    </div>
</div>
</template>

<script>

export default {
  name: "Header",
  


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>