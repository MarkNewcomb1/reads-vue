<template>
<div>
    <Header />
    <router-view></router-view>
    <h1>This be home</h1>
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
</style>