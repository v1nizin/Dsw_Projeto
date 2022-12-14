<script>
import SerieApi from "../api/series.js";
const seriesapi = new SerieApi();
export default {
  data() {
    return {
      videos: false,
    };
  },
  props: ["serie"],
  
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
      :src="getPosterUrl(serie.poster_path)"
      />
      <div class="descMovi11">
        <h1 class="titulo2">{{ serie.name}}</h1>
        <div class="descMovi9">
          <h1>Sinopse:</h1>
          <p>
            {{ serie.overview}}
          </p>
        </div>
        <div class="descMovi8">
          <h3>Lançamento: {{ serie.first_air_date}}</h3>
      </div>
      <div class="descMovi7">
          <h3>Temporadas: {{serie.number_of_seasons}}</h3>
      </div>
        <div class="descMovi7">
          <h3>Avaliação dos usuários: {{ Math.round(serie.vote_average) }}</h3>
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
  margin-top: 5px;
}
.descMovi8 {
  color: white;
}
.descMovi7 {
  color: white;
  }



</style>