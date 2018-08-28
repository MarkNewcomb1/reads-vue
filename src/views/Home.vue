<template>
<div>
    <Header />
    <router-view></router-view>
    <div class="flex-row">
        <a href="/authors" class="flex-column">
        <img src="../assets/author-placeholder.jpg" alt="authors" />
            <h2>Authors</h2>
        </a>
        <a href="/books" class="flex-column">
        <img src="../assets/book-placeholder.png" alt="books" />
            <h2>Books</h2>
        </a>
    </div>
</div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header';

export default {
    name: "Home",
    components: {
    Header
    }
};
</script>

<style scoped>
.flex-row {
    display: flex;
    justify-content: space-between;
}
</style>