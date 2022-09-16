<script setup lang="ts">

    import { ref } from "@vue/reactivity";
    
    import Card from "./card.vue";
    // On fait une variable réactive qui réference les données
    // ATTENTION : faire une Ref pas une Reactive car :
    // c'est l'objet qui doit être réactif, pas ses props
    const maison = ref({nom:"Nom de la maison", price:50000, favoris:false, txt:"texte de description",nbbed:2, nbbath:4,  nbsize:"200 m²", img:"/public/maison.jpg"});
</script>
<template>
    <div>
        <div class="p-2">
            <h2 class="text-4xl text-center text-red-800 shadow-2xl mb-16 ">Résultat (Prévisualisation)</h2>
            <!-- Optionnel on affiche les données -->
            <Card v-bind="maison" />
        </div>
     <div class="p-4 text-center text-blue-600 mt-10 bg-blue-100 rounded-2xl">
        <!-- On passe la "ref" à FormKit -->

        
        <FormKit type="form"
        
        :submit-attrs="{ classes: { input: 'bg-red-500 animate-bounce  p-2 rounded text-center px-16 py-4 text-black mt-12 ' } }" 
        
        :config="{classes: {
            
        input: 'p-2 rounded  border-black-300 shadow-sm border hover:bg-indigo-300', 
        label: 'text-indigo-700'}}" v-model="maison" >

<div class=" pt-6 pb-6 text-xl">
           <FormKit  name="nom" label="Nom" />
</div>
<div class=" pt-6 pb-6 text-xl">
           <FormKit name="price" label="Prix" type="number" />
 </div>
<div class=" pt-6 pb-6 text-xl">
           <FormKit name="txt" label="Description Maison"/>
</div>
<div class=" pt-6 pb-6 text-xl">
           <FormKit name="nbbath" label="Nombre de salle de bain" type="number" />
</div>
        <div class=" text-center flex text-white justify-center text-xl">
           <FormKit  name="favoris" label="Ajouter aux favoris"
           type="checkbox"  wrapper-class="flex" :submit-attrs="{ classes: { input: 'bg-red-600 p-1 rounded  ' } }"
        
 />
</div>
        </FormKit>
     </div>
    </div>
</template>