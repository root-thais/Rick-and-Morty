<template>
    
    <div class="row">
    <div class="col-xs-12">
        <div class="input-group mb-3">
            <input type="text" class="form-control" v-model="name" placeholder="Nome do personagem" >
            <button class="btn btn-outline-secondary" type="button" id="button-addon2" @click="firstSearch()">Buscar</button>
        </div>
    </div>
    
    <div class="col-xs-12">
        <p class="text-center  text-white">Total: {{ total_character }}</p>
        <div class="list-group">
            <a v-for="(character, i) in characters" :key="i" href="#" class="list-group-item list-group-item-action" aria-current="true">
                <div class="d-flex w-100 justify-content-between">
                    <div class="d-flex">
                        <img :src="character.image" class="img-fluid image" alt="">
                        <div>
                            <h5 class="mb-1">{{ character.name }}</h5>
                            <p>Genero: {{ character.gender }}</p>
                        </div>
                    </div>
                </div>
                <p class="mb-1">especie: {{ character.species }}</p>
                <small>tipo: {{ character.type }}</small>
            </a>
        </div>
    </div>

    <div class="col-xs-12 mt-3 mb-10 text-center">
        <div class="btn-group" role="group" aria-label="Basic outlined example">
            <button @click="goToPrev()" :disabled="!has_prev" type="button" class="btn btn-primary"> {{ '<' }} </button>
            <button type="button" disabled class="btn btn-primary">{{page}}</button>
            <button @click="goToNext()" :disabled="!has_next" type="button" class="btn btn-primary"> > </button>
        </div>
    </div>


</div>
  
</template>

<script setup>
import axios from 'axios';
import { ref } from 'vue';

const name = ref("")
const total_character = ref(0)
const characters = ref([])
const page = ref(1)
const has_next = ref(false)
const has_prev = ref(false) 

const goToNext =() => {
    page.value += 1

    searchCharacter()
}

const goToPrev =() => {
    page.value -= 1

    searchCharacter()
}

const firstSearch =() =>{
    page.value = 1

    searchCharacter()
}


const searchCharacter = async() => {
    characters.value = []
    const response = await axios.get("https://rickandmortyapi.com/api/character", {
        params: {
            name: name.value,
            page: page.value
        }
    })
    
    console.log(response.data.info)
    total_character.value = response.data.info.count
    has_next.value = !!response.data.info.next
    has_prev.value = !!response.data.info.prev
    characters.value = response.data.results

}

</script>

<style scoped>
.image{
    max-width: 5rem;
    margin-right: 1rem;
}

.mb-10{
    margin-bottom: 8rem;
}

</style>