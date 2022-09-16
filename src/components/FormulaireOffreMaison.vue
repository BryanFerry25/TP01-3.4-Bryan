<script setup lang="ts">

    import { ref } from "@vue/reactivity";
    
    import Card from "./card.vue";
    // On fait une variable réactive qui réference les données
    // ATTENTION : faire une Ref pas une Reactive car :
    // c'est l'objet qui doit être réactif, pas ses props
    const maison = ref({nom:"test-ref-formkit", price:50000, favoris:false, txt:"texte de description",nbbed:2, nbbath:4,  nbsize:"200 m²", img:"/public/maison.jpg"});
</script>
<template>
    <div>
        <div class="p-2">
            <h2 class="text-4xl text-center text-red-800 shadow-2xl mb-16 ">Résultat (Prévisualisation)</h2>
            <!-- Optionnel on affiche les données -->
            <Card v-bind="maison" />
        </div>
     <div class="p-2">
        <!-- On passe la "ref" à FormKit -->
        <FormKit type="form"
        
        :submit-attrs="{ classes: { input: 'bg-red-300 p-2 rounded text-center' } }" 
        
        :config="{classes: {
            
        input: 'p-2 rounded  border-black-300 shadow-sm border hover:bg-indigo-300', 
        label: 'text-indigo-700'}}" v-model="maison" >


           <FormKit name="nom" label="Nom" />

           <FormKit name="price" label="Prix" type="number" />

           <FormKit name="txt" label="Description Maison"/>

           <FormKit name="nbbath" label="Nombre de salle de bain" type="number" />
           <FormKit name="favoris" label="Ajouter aux favoris"
           type="checkbox"  wrapper-class="flex" :submit-attrs="{ classes: { input: 'bg-red-300 p-1 rounded' } }"
 />
        </FormKit>
     </div>
    </div>
</template>