<template>
<div>
    <Header />
    <router-view></router-view>
    <AuthorsComponent />
    <!-- <Footer /> -->
</div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header';
import AuthorsComponent from '@/components/AuthorsComponent';

export default {
    name: "books",
    components: {
    Header,
    AuthorsComponent
    },
    data() {
        return {
            authors: null,
            apiURL: "https://galvanize-reads-mark.herokuapp.com/authors"
        };
    },
    mounted() {
    fetch(this.apiURL)
        .then(response => response.json())
        .then(response => {
        this.authors = response;
        });
    }
};
</script>

<style scoped>
</style>