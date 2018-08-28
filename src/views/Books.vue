<template>
<div>
    <Header />
    <router-view></router-view>
    <BooksComponent />
    <!-- <Footer /> -->
</div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header';
import BooksComponent from '@/components/BooksComponent';

export default {
    name: "books",
    components: {
    Header,
    BooksComponent
    },
    data() {
        return {
            books: null,
            apiURL: "https://galvanize-reads-mark.herokuapp.com/books"
        };
    },
    mounted() {
    fetch(this.apiURL)
        .then(response => response.json())
        .then(response => {
        this.books = response;
        });
    }
};
</script>

<style scoped>
</style>