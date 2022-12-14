<script>
import FilmeApi from "../api/filmes.js";
const filmeapi = new FilmeApi();
export default {
  data() {
    return {
      videos: false,
    };
  },
  props: ["filme"],
  
  methods: {
    
    getPosterUrl(posterPath) {
      return `https://image.tmdb.org/t/p/w500${posterPath}`;
    },
  
   
},
}
</script>
<template>
  <div class="descMovi10">
    <img
    class="poster-filme-pag"
    :src="getPosterUrl(filme.poster_path)"
    />
    <div class="descMovi11">
      <h1 class="titulo2">{{ filme.title }}</h1>
      <div class="descMovi9">
        <h3>Sinopse:</h3>
        <p>
          {{ filme.overview }}
        </p>
      </div>
      <div class="descMovi8">
        <h3>Lançamento: {{ filme.release_date }}</h3>
      </div>
      <div class="descMovi7">
        <h3>Avaliação dos usuários: {{ Math.round(filme.vote_average) }}</h3>
      </div>
    </div>
  </div>    
</template>

<style>
.descMovi11 {
  display: flex;
  padding: 41px;
  flex-direction: column;
}
.descMovi10{
  display: flex;
  padding: 41px;
}
.descMovi9 {
  color: white;


}
.descMovi8 {
  color: white;
}
.descMovi7 {
  color: white;
  }

</style>