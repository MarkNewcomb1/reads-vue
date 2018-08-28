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
    }
};
</script>

<style scoped>
</style>