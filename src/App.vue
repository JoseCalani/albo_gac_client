<template>
  <div>
    
  <div v-for="usuario in placeholders" v-bind:key="usuario.id_usuario">
  <span>{{ usuario.id_usuario}}</span><button>
  {{ usuario.nombres }}</button><br/>
  </div>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  components: {
  
  },
  data(){
    return {
      placeholders: []
    }
  },
  methods: {
    async getPlaceholders () {
      const reponse = await axios.get('https://albo-gac-api.herokuapp.com/api/usuario/')
      this.placeholders = reponse.data
    }
  },
  created(){
    this.getPlaceholders()
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
</style>
