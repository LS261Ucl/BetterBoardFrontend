<template v-slot="singleObj">
    <div class="quote" >
        <p>just a test</p>
        <h1>{{id}}</h1>
    </div>
</template>

<script>
    export default {
        name: 'singleqoute',
        props: {
            single: Object,
        }
    }
</script>

<style scope>
    .fas {
        color: darkblue;
    }

    .qoute {
        background: #f4f4f4;
        margin: 5px;
        padding: 10px 20px;
        cursor: pointer;
    }
       .qoute h3 {
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
</style>