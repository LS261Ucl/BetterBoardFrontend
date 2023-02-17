<template>
    <div class="qoute">
        <div :key="qoute.id" v-for="qoute in qoutes">
            <h3>{{qoute.qoute}}</h3>
            <p>{{qoute.author}}</p>

            <!--<Qoute :qoute="qoute" />-->
        </div>
    </div>
   
</template>



<script>

    import SingleQoute from './SingleQoute'

    export default {
        name: 'Qoutes',
        props: {
            qoutes: Array
        },
        compontens: {
             SingleQoute
        },
        methodes:
        {


            //trouble using
        //function getRandomElement(qoute) {
        //const index = Math.floor(Math.random() * (qoute.lengt))
        //const randomElement = qoute[index];
        //return randomElement;
    }
    }
    


</script>

<style>
    .qoute {
        background: #f4f4f4;
        margin: 5px;
        padding: 10px 20px;
        cursor: pointer;
    }
</style>