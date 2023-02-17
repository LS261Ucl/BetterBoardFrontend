<template >
    <div class="container">
        <Header titel="Superhero Qoutes"/>
        <!--<Qoutes :qoutes="qoutes"/>
        <SingleQoute :single="singleqoute"/>-->
        <h1 v-bind:for="qoute">{{single.qoute}}</h1>
        <p>{{single.author}}</p>
    </div>

</template>

<script>
    import Header from './components/Header'
    //import Qoutes from './components/Qoutes'
    //import SingleQoute from './components/SingleQoute'

export default {
  name: 'App',
  components: {
      Header,
      //Qoutes,
      //SingleQoute
        },

    data() {
        return {
            qoutes: [],
            single: Object,
            // qoutes: []
            timer: ''
        }
        },
        methods: {
            //async fetchQoutes() {
            //    const res = await fetch('https://localhost:5001/api/SuperheroQoute/qoutes')
            //    const data = await res.json()
            //    return data
            //},
            async fetchSingleQoute() {
                    const res = await fetch('https://localhost:5001/api/SuperheroQoute/singleqoute')
                    const data = await res.json()
                    console.log(data)
                    this.single = data
                    return data
            },
            cancleAutoUpdate() {
                clearInterval(this.timer)
            }
        },    
        async created() {
            //this.qoutes = await this.fetchQoutes()
            this.single = await this.fetchSingleQoute()
            this.timer = setInterval(this.fetchSingleQoute, 10000)

        }
        
}
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;   
    }

    .container {
        max-width: 500px;
        margin: 30px auto;
        overflow: auto;
        min-height: 300px;
        border: 1px solid steelblue;
        padding: 30px;
        border-radius: 5px;
    }
</style>
