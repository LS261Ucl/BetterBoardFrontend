<template>
 <header>
     <h1>{{titel}}</h1>
 </header>
</template>

<script>
    export default {
        name: "Header",
        props: {
            titel: String,
        }
    }
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>