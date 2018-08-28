<template>
    <ul>
    <li v-for="book in books" :key="book.id">
        <img :src=book.bookCoverUrl />
        <h2>{{ book.bookTitle }}</h2>
        <h3>{{ book.bookGenre }}</h3>
        <span>By {{ book.author1FirstName}} {{ book.author1LastName}}</span><span v-if="book.author2FirstName !== null">, {{ book.author2FirstName}} {{ book.author2LastName}}</span><span v-if="book.author3FirstName !== null">, {{ book.author3FirstName}} {{ book.author3LastName}}</span>
        <p>{{ book.bookDescription }}</p>
    </li>
    </ul>

</template>

<script>
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
h3 {
  font-style: italic;
}
</style>