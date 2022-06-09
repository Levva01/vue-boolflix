<template>
  <header>

      <form @submit.prevent="submit()">                     
          <input class="" type="text" placeholder="Inserisci il titolo" v-model="searchBar">
          <button type="submit">Invia</button>                 
      </form>

  </header>
</template>

<script>

import axios from 'axios';
import search from "../../shared/search";

export default {
    name: 'BaseHeader',
    data(){
        return {
            searchBar: '',
            search
        }
    },

     methods: {
        submit() {
            axios.get('https://api.themoviedb.org/3/search/movie',
                {
                    params: {
                        api_key: 'a7a419e37d72e1c36a8e9d8a86beb8d5',
                        query: this.searchBar,
                        language: 'it-IT'
                    }
                }
            ).then((response) => {
                search.films = response.data.results;
            }).catch((error) => {
                console.log(error);
            })
        }
    }
}
</script>

<style lang="scss" scoped>

</style>