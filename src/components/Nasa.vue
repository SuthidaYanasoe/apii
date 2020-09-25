<template>
<div class="Nasa">
    <div>

        <b-navbar toggleable="lg" type="black" variant="black">
            <a class="logo">
                <img src="https://is2-ssl.mzstatic.com/image/thumb/Purple114/v4/17/e8/23/17e8236a-b57d-2d36-c679-7263fd196c69/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.jpeg/246x0w.jpg" width="60" height="60" alt="">
            </a>
            <b-navbar-brand href="#"> Nasa</b-navbar-brand>
        </b-navbar>

        <form v-on:submit.prevent="getResult(query)">
            <input type="text" placeholder="search........." v-model="query"   />
        </form>
        <div class="results" v-if="results">
            <div v-for="result in results" v-bind:key="result">
                <img v-bind:src="result.links[0].href" >
            </div>
        </div>
    </div>
    
</div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Nasa',
    data() {
        return {
            msg: 'Nasa',
            query: '',
            results: ''
        }
    },
    methods: {
        getResult(query) {
            axios.get('https://images-api.nasa.gov/search?q=' 
            + query + '&media_type=image').then(response => {
                console.log(response.data.collection.items);
                this.results = response.data.collection.items.slice(0,20);
          
            });
        }
        

    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
.results img {
    height: 300px;
    margin: 10px;
}

h1,
h2 {
    font-weight: normal;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}
</style>
