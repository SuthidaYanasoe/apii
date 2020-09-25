<template>
  <div id="app">
    <Nasa></Nasa>
   <vs-card-group>
      <template #title>
        <h3>Pot with a plant</h3>
      </template>
      <template #img>
        <img :src="`/foto${card}.png`" alt="">
      </template>
      <template #text>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit.
        </p>
      </template>
      <template #interactions>
        <vs-button danger icon>
          <i class='bx bx-heart'></i>
        </vs-button>
        <vs-button class="btn-chat" shadow primary>
          <i class='bx bx-chat' ></i>
          <span class="span">
            54
          </span>
        </vs-button>
      </template>
      <template>
        
      </template>
    
  </vs-card-group>

  </div>
</template>

<script>
import Nasa from './components/Nasa'


export default {
  name: 'app',
  components: {
    Nasa
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0px;
  background: url(https://media0.giphy.com/media/RHIKETUlUINYvV7CAO/giphy.gif)  no-repeat center fixed;
      background-repeat: no-repeat;
      background-size: cover;
  
 
}


</style>
