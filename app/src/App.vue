<template>
  <!-- <TheHeader></TheHeader>  Nota: Dos dois jeitos funcionam nesse caso-->
  <!--  v-show altera a propriedade de estilo para display:none, ou seja, o elemento existe no DOM diferente do v-if-->
  <TheHeader 
    v-if="showHeader"
  />
  <div v-show="showName">
    Nome: {{ firstName }}
    <br>
    Sobrenome: {{ lastName }}
  </div>

  <div v-if="accessLevel === 'Admin'">Admin</div>
  <div v-else-if="accessLevel === 'Marketing'">Marketing</div>
  <div v-else>User</div>

  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App" />
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TheHeader
  },
  data(){
    return{
      showHeader: true,
      firstName: "Bruno",
      lastName: "Cruz",
      showName: false,
      accessLevel: 'Admin'
    }
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
