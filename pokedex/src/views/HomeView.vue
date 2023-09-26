<script setup>

import { onMounted, reactive, ref } from 'vue';
import ListPokemons from '../components/ListPokemons.vue';

let baseUrlSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/")
let pokemons = reactive(ref());

onMounted(() => {
    fetch("https://pokeapi.co/api/v2/pokemon/?limit=20&offset=20")
    .then(response => response.json())
    .then(response =>{
        pokemons.value = response.results
        console.log(resp);
    })
})

</script>

<template>
    <main>
        <div class="container">
            <div class="row mt-4">git remote add origin https://github.com/JanuarioMarcos/Trabalho.git
git branch -M main
git push -u origin main
                <div class="col-sm-12 col-md-6">
                    <div class="card" >
                        <div class="card-body row">
                            <ListPokemons
                            v-for="pokemon in pokemons"
                            :key="pokemon.name"
                            :name="pokemon.name"
                            :baseUrlSvg="baseUrlSvg+pokemon.url.split('/')[6]+'.svg'"
                            
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>  
</template>
