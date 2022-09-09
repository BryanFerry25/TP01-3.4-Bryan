<template>
        <div class="p-2">

        <h1 class="text-2xl">Page Liste</h1>

        <div v-for="maisons in maisons" 
        :key="maisons.nom">


            <card class="w-1/2" v-bind="maisons"/>

        </div>
    </div>
</template>

<script setup lang="ts">

import card from "../components/card.vue";

const maisons = [{nom:"Maison", price:5000, favoris:true, txt:"Belle Maison", nbbath:3, nbsize:"500 m²", img:"/public/maison.jpg"}, {nom:"Maison 2", price:4500, favoris:false, txt:"Agréable maison", nbbath:1, nbsize:"300 m²", img:"/public/maison2.jpg"},{nom:"Maison 3", price:6000, txt:"Magnifique maison", favoris:true, nbbath:5, nbsize:"700 m²", img:"/public/maison3.jpg"},{nom:"Maison 4", price:2000, txt:"Basique maison", nbbath:2, nbsize:"100 m²", img:"/public/maison4.jpg"}]


</script>