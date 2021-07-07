<template>
    <div @click="showNutrientes()" class="content">
        <h1 class="title is-4 has-text-centered">{{nome}}</h1>
        <div class="content is-small hidden has-text-centered is-hidden">
            <h1 class="subtitle is-6">Tabela nutricional</h1>    
            <ul class="">
                <li class="has-text-left">Calorias: {{calorias}} Kcal</li>
                <li class="has-text-left">Carboidratos: {{carboidratos}}g</li>
                <li class="has-text-left">Proteínas: {{proteinas}}g</li>
                <li class="has-text-left">Gorduras: {{gorduras}}g</li>
                <li class="has-text-left">Fibras: {{fibras}}g</li>
            </ul>
        </div>
        <!-- <button class="button is-info is-light is-small is-fullwidth" >Mostar mais</button> -->
    </div>
</template>

<script>
export default {
    props: {
        id: String,
        nome: String,
        calorias: String,
        carboidratos: String,
        proteinas: String,
        gorduras: String,
        fibras: String
    },
    methods: {
    showNutrientes() {
        if(this.$el.children[1].classList.value.indexOf('animation') == -1) {
            this.$el.children[1].classList.remove('is-hidden');
            this.$el.children[1].classList.add('animation');
        } else {
            this.$el.children[1].classList.remove('animation');
        }
    }
  }
}
</script>
<style>
div.content {
    cursor: pointer;
}
ul {
    display: inline-block;
}
.hidden {
    max-height: 0px;
    animation-name: hidden;
    animation-duration: 0.5s;
    animation-fill-mode: forwards;
    overflow: hidden;
}
.animation {
    animation-name: show;
    animation-duration: 0.5s;
    display: block;
    animation-fill-mode: forwards;
}
.title {
    margin: 0px;
}
.title, .subtitle {
    color: hsl(0, 0%, 100%)!important
}
@keyframes show {
    from {
        max-height: 0px;
    }
    to {
        max-height: 500px;
    }
}
@keyframes hidden {
    from {
        max-height: 500px;
        }
    to {
        max-height: 0px;
    }
}
</style>