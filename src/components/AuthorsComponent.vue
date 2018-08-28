<template>
    <ul>
    <li v-for="author in authors" :key="author.id">
        <img :src=author.portraitUrl />
        <h2>{{ author.firstName }} {{ author.lastName}}</h2>
        <p>{{ author.biography }}</p>
        <h6>Books</h6>
        <span v-if="author.books !== null">{{ author.books}}</span><span v-if="author.moreBooks !== null">{{ author.moreBooks }}</span><span v-if="author.evenMoreBooks !== null">{{ author.evenMoreBooks }}</span>
    </li>
    </ul>

</template>

<script>
import router from '../router';

export default {
  name: 'AuthorsComponent',
  data() {
    return {
      authors: [],
      apiURL: 'https://galvanize-reads-mark.herokuapp.com/authors'
    };
  },
  mounted() {
    fetch(this.apiURL)
      .then(response => response.json())
      .then(response => {
        this.authors = response.authors;
      });
  },
};
</script>

<style scoped>
</style>