<template>
  <main>
    <h4>Films</h4>
    <ul>
        <li class="" v-for="film in search.films" :key="film.id">{{film.title}} , {{film.original_title}} , {{film.original_language}} , {{film.vote_average}}</li>
    </ul>

    <h4>Tv Series</h4>
    <ul>
      <li class="" v-for="series in search.tvSeries" :key="series.id">{{series.name}} , {{series.original_name}} , {{series.original_language}} , {{series.vote_average}}</li>
    </ul>
  </main>
</template>


<script>

import search from "../../shared/search";

export default {
    name: 'BaseMain',
    components: {
    },
    data(){
        return {
            search
        }
    },
    
}
</script>

<style lang="scss" scoped>

</style>