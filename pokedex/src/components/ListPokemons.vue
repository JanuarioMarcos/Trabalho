<script setup>

const pokemon = defineProps(["name","baseUrlSvg"]);

</script>

<template>
    <div class="col-4">
        <div class="card mb-3">
            <p class="text-center">{{ pokemon.name }}</p>
            <img :src="baseUrlSvg" alt="..." class="card-img-top" height="80">
        </div>
    </div>
</template>

<style>

</style>