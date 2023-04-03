<script >
import {ref,watchEffect} from 'vue';
const API_URL='https://rickandmortyapi.com/api/character/';

const commits=ref(null);


watchEffect(async ()=>{

    const url=`${API_URL}`;
    commits.value=await (await fetch(url)).json();
})


</script>
<template>
    <h1>Lista de personajes</h1>

        
        <ul >
            <li v-for="{name, image,gender} in commits">
            <span>{{commit.name}}</span>
            <span>{{commit.gender}}</span>
            <img src={{commit.image}}/>

            </li>
        </ul>
    
</template>