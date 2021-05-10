<template>
  <div>
        <h1>Upcoming Movies</h1>
        <div v-for="movie in movies" :key=movie.id>
            <h4>{{movie.titles}}</h4>
            <p> {{movie.id}}</p>
        </div>
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
    Mounted()
    {
        axios.get("https://api.themoviedb.org/3/movie/now_playing?api_key=4e44efca8c5b5ab2f9bdba7250e3b882&language=en-US&page=1")
        .then( response => {
            console.log(response);
            this.movies = response.data.results;
        })
    }

}
</script>

<style>

</style>