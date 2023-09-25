<script setup>
const personagem = defineProps(["name"])
</script>

<template>
    <div class="col-4">
        <div class="card mb-3">
            <p class="texte-center">{{ personagem.name }}</p>
            <img src=" " class="card-img-top" height="80">   
        </div>
    </div>

</template>

<style>

</style>