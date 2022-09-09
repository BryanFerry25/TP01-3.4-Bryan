<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Simple</h1>


        <card class="w-1/2" v-bind="objet"/>

    </div>
    </template>
    
    <script setup lang="ts">
        import card from "../components/card.vue";
    
        const objet = {nom:"Maison", favoris:true, price:4000, nbsize:"200 m²", txt:"Joli maison", nbbath:2, img:"/public/maison.jpg"}
    </script>