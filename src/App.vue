<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->

  <!-- for dynamic components we have to use the name of 
  activeTab variable as like as we imported that component ,
  we can also use our liked variable name in normal componnet calling-->

<button @click="activeTab='Jasmine'">Jasmine</button>
<button @click="activeTab='Rose'">Rose</button>
<button @click="activeTab='tulip'">Tulip</button>
<button @click="activeTab='Inputpage'">Input</button>

<!-- normal calling of component  -->

<!-- <Jasmine v-if="activeTab ==='Jasmine'"/>
<Rose v-if="activeTab ==='Rose'"/>
<tulip v-if="activeTab ==='tulip'"/> -->


<!-- dynamic components -->
<component :is="activeTab" />

<!-- when switching tab or tab inactivity the value in that page is cleared 
or new instance is created on each click ,this is desired but when we create 
multiple page form filling ,we have to keep the value in that page at that we can use 'keep-alive' -->
<keep-alive>
<alive v-if="activeTab ==='Inputpage'"/>
</keep-alive>


</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Jasmine from './components/Jasmine.vue'
import Rose from './components/Rose.vue'
import tulip from './components/tulip.vue'
import alive from './components/keeplivepage.vue'

export default {
  name: 'App',
  components: {
    Jasmine,
    Rose,
    tulip,
    alive
},
  data(){
    return{
      activeTab:'Jasmine'
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
