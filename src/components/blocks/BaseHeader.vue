<template>
  <header class="header">

      <div class="header__logo">BOOLFLIX</div>

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
                        api_key: 'e090893db0c1d71a802be9a80e29d0b7',
                        query: this.searchBar,
                        language: 'it-IT'
                    }
                }
            ).then((response) => {
                search.films = response.data.results;
            }).catch((error) => {
                console.log(error);
            }),

            axios.get('https://api.themoviedb.org/3/search/tv',
                {
                    params: {
                        api_key: 'e090893db0c1d71a802be9a80e29d0b7',
                        query: this.searchBar,
                        language: 'it-IT'
                    }
                }
                ).then((response) => {
                    search.tvSeries = response.data.results;
                }).catch((error) => {
                    console.log(error);
            })
        }
    }
}
</script>

<style lang="scss" scoped>

    .header{

        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: black;
        padding: .625rem;


        &__logo{
            color: red;
            font-size: 1.875rem;
        }
    }

</style>