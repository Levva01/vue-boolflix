<template>
  <main>
    <ul>
        <li class="" v-for="film in search.films" :key="film.id">{{film.title}} , {{film.original_title}} , {{film.original_language}} , {{film.vote_average}}</li>
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