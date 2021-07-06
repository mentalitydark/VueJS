<template>
    <div class="">
        <h1 class="title text-centered">{{nome}}</h1>
        <ul class="text-centered">
            <li>Calorias: {{calorias}} Kcal</li>
            <li>Carboidratos: {{carboidratos}}g</li>
            <li>Proteínas: {{proteinas}}g</li>
            <li>Gorduras: {{gorduras}}g</li>
            <li>Fibras: {{fibras}}g</li>
            <li>Sódio: {{sodio}}mg</li>
            <li>Cálcio: {{calcio}}mg</li>
            <li>Ferro: {{ferro}}mg</li>
            <li>Fósforo: {{fosforo}}mg</li>
            <li>Magnésio: {{magnesio}}mg</li>
            <li>Selênio: {{selenio}}mcg</li>
            <li>Potássio: {{potassio}}mg</li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        id: Number,
        nome: String,
        calorias: Number,
        carboidratos: Number,
        proteinas: Number,
        gorduras: Number,
        fibras: Number,
        sodio: Number,
        calcio: Number,
        ferro: Number,
        fosforo: Number,
        magnesio: Number,
        selenio: Number,
        potassio: Number
    }
}
</script>