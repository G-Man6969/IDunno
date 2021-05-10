<template>
  <div>
      <h1>Upcoming Movies</h1>
        <p v-for="movie in movies" :key="movie.id">{{movies.titles}}</p>
 </div>
</template>

<script>
import axios from "axios"
export default {
    name:'Movies',
    data()
    {
        return{
            movies:[]
        }
    },
    mounted()
    {
        acios.get("https://api.themoviedb.org/3/movie/latest?api_key=4e44efca8c5b5ab2f9bdba7250e3b882&language=en-US")
        .then( response => {
            console.log(response);
            this.movies = response.data.results;
        })
    }

}
</script>

<style>

</style>