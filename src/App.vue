<template>
  <div id="app" class="is-dark">
    <Header></Header>
    <div class="container is-mobile is-flex is-flex-direction-row is-flex-wrap-wrap light">
      <div v-on:click="showElement" v-for="(alimento, index) in alimentos" :key="index" class="column border-line min-w">
        <Alimento :id="alimento.id" :nome="alimento.nome" :calorias="alimento.calorias" :carboidratos="alimento.carboidratos"
        :proteinas="alimento.proteinas" :gorduras="alimento.gorduras" :fibras="alimento.fibras"/>
      </div>
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
  },
  methods: {
    showElement: function(element) {
      if(element.path[0].className == "column border-line min-w") {
        if(element.path[0].firstChild.lastChild.classList.value.indexOf('animation') == -1) {
          element.path[0].firstChild.lastChild.classList.remove('is-hidden');
          element.path[0].firstChild.lastChild.classList.add('animation');
        } else {
          element.path[0].firstChild.lastChild.classList.remove('animation');
        }
      }
    }
  }
}
</script>


<style>
html, body {
  min-height: 100vh;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow: hidden;
  background: hsl(0, 0%, 93%);
  background-color: hsl(0, 0%, 30%);
  min-height: 100vh;
}
.light {
  background-color: hsl(0, 0%, 30%);
  color: hsl(0, 0%, 100%);
}
.border-line {
  box-sizing: border-box;
  border: 0.1px solid rgba(0, 0, 0, 0.3);
}
.min-w {
  min-width: 185px;
}
.min-w:hover {
  cursor: pointer;
  background-color: hsl(0, 0%, 40%);
}
@media screen and (max-width: 370px) {
  .min-w{
    text-align: center;
  }
  ::marker{
    content: '';
  }
}
</style>
