<template>
  <div>
      <h1>Movie Detail</h1>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'Detail',
    data(){
        return{
            id:""
        }
    },
    mounted()
    {
        axios.get("https://api.themoviedb.org3/movie/{movie_id}?api_key")
    }
}
</script>

<style>

</style>