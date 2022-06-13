<template>
  <main>
    <h4>Films</h4>
    <ul class="film-list">
      <li v-for="film in search.films" :key="film.id">
        <BaseCard :info="film"/>
      </li>
    </ul>

    <h4>Tv Series</h4>
    <ul class="tvSeries-list">
      <li v-for="serie in search.tvSeries" :key="serie.id">
        <BaseCard :info="serie"/>
      </li>
    </ul>
  </main>
</template>


<script>

import BaseCard from '../commons/BaseCard.vue';
import search from "../../shared/search";

export default {
    name: 'BaseMain',
    components: {
      BaseCard,
    },
    data(){
        return {
            search
        }
    },
    
}
</script>

<style lang="scss" scoped>

  main{
    background-color: #303030;
  }

  .film-list{
    display: flex;
    flex-wrap: wrap;
    gap: 4.375rem;
    li{
      list-style: none;
      color: white;
      font-size: .75rem;
    }
  }

  .tvSeries-list{
    display: flex;
    flex-wrap: wrap;
    gap: 4.375rem;
    li{
      list-style: none;
      color: white;
      font-size: .75rem;
    }
  }

</style>