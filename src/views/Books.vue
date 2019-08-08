
<template>
  <div class="home">
    <h1>Harry Potter Books</h1>
    <div v-for="books in book">
      <h2>{{ books.name }}</h2>
      <img v-bind:src="books.url">
      <p>Name: {{ books.name }}</p>
      <p>Page: {{ books.page_numbers }}</p>.
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data: function() {
    return {
      books: []
    };
  },
  created: function() {
    axios.get("/api/photos").then(response => {
      this.photos = response.data;
    });
  },
  methods: {

  }
};
</script>
