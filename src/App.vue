<template>
  <div id="app" class="">
    <Header></Header>
    <div v-for="(alimento, index) in alimentos" :key="index" class="">
      <Alimento :id="alimento.id" :nome="alimento.nome" :calorias="alimento.calorias" :carboidratos="alimento.carboidratos"
      :proteinas="alimento.proteinas" :gorduras="alimento.gorduras" :fibras="alimento.fibras" :sodio="alimento.sodio" :calcio="alimento.calcio"
      :ferro="alimento.ferro" :fosforo="alimento.fosforo" :magnesio="alimento.magnesio" :selenio="alimento.selenio" :potassio="alimento.potassio"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Alimento from './components/Alimento.vue'
import Header from './components/Header.vue'
document.addEventListener('DOMContentLoaded', () => {
  const navbarBurgers = document.querySelector('.navbar-burger');
  navbarBurgers.addEventListener('click', () => {
    const target = navbarBurgers.dataset.target;
    const $target = document.getElementById(target);
    navbarBurgers.classList.toggle('is-active');
    $target.classList.toggle('is-active');
  });
});

export default {
  name: 'App',
  data(){
    return {
      alimentos: []
    }
  },
  created: function(){
    axios.get('http://179.216.101.250:3000/').then(res => {
      this.alimentos = (res.data);
    });
  },
  components: {
    Alimento,
    Header
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow: hidden;
}
</style>
