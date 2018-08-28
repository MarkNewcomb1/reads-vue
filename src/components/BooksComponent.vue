<template>
    <ul>
    <li v-for="book in books" :key="book.id">
        <h2>{{ book.bookTitle }}</h2>
        <h3>{{ book.bookGenre }}</h3>
        <p>{{ book.bookDescription }}</p>
    </li>
    </ul>

</template>

<script>
import router from '../router';

export default {
  name: 'BooksComponent',
  data() {
    return {
      books: [],
      apiURL: 'https://galvanize-reads-mark.herokuapp.com/books'
    };
  },
  mounted() {
    fetch(this.apiURL)
      .then(response => response.json())
      .then(response => {
        this.books = response.books;
      });
  },
};
</script>

<style scoped>
</style>