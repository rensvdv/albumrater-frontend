<template>
  <div class="albums">
    <div v-for="album in albums" :key="album.id">
      <h2>{{ album.id }} {{ album.title }}</h2>
      <p>{{ album.artist }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "AlbumView",
  data() {
    return {
      albums: []
    }
  },
  mounted() {
    axios.get('http://localhost:8080/api/albums')
        .then((response) => {
          this.albums = response.data
        })
  }
}
</script>

<style scoped>

</style>