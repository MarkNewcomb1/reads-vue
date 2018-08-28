<template>
    <ul>
    <li v-for="author in authors" :key="author.id">
        <h2>{{ author.firstName }} {{ author.lastName}}</h2>
        <p>{{ author.biography }}</p>
        <img :src=author.portraitUrl />
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