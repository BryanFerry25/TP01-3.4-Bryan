<template>
    <div class="p-5">
        <h1 class="text-2xl">Page Liste Supabase</h1>
        <div v-for="maisons in Tableaudesmaisons" :key="maisons.nom">
            <card class="w-1/2 mb-10" v-bind="maisons"/>
        </div>
    </div>
</template>

<script setup lang="ts">
    import card from "../components/card.vue"
    import { supabase } from "../supabase";
    console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code
    //const maisons = []; // à remplacer par l'appel à Supabasebite

    let { data: Tableaudesmaisons, error:error } = await supabase
  .from('Maison')
  .select('*')

  console.log(Tableaudesmaisons)

</script>