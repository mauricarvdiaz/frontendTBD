<template>
  <div class="center">
    <h2>{{title}}</h2>
    
    <!--<ul class="list-group">
      <li v-for="u, i in films">
        <img :src="'https://robohash.org/'+i+'?size=50x50'" />
        <span>{{u.firstName}} {{u.lastName}}</span>
        <span class="date">{{Date(u.lastUpdate)}}</span>
      </li>
    </ul> -->
      <div v-for="movie in films">
        <div class="card border-secondary mb-3" style="max-width: 18rem;">
          <div class="card-header">Año {{movie.release_year}}</div>
          <div class="card-body text-secondary">
            <h5 class="card-title">{{movie.title}}</h5>
            <p class="card-text">{{movie.description}}</p>
          </div>
        </div>
      </div>
  </div>
</template>
<script>
export default {
  data(){
    return{
      title:'Peliculas',
      films:[]
    }
  },
  mounted:function(){
    console.log('Index.vue');
    // GET /someUrl
    this.$http.get('http://localhost:8081/sakila-spring-backend/films')
    .then(response=>{
       // get body data
      this.films = response.body;
     console.log('Peliculas cargadas')
    }, response=>{
       // error callback
       console.log('error cargando lista');
    })
  }
}
</script>
