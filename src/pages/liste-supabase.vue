
<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Liste</h1>
        <div v-for="maison in maisons" :key="maison.nom">
            <card class="w-1/2" v-bind="maison"/>
        </div>
    </div>
    </template>





<script>

import { supabase } from "../supabase";

console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code



const maisons = []; // à remplacer par l'appel à Supabase

</script>