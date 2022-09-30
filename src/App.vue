<template>
  <nav>
    <h4 class="text-xl">
      <Bars3Icon class="inline-block h-5 w-5 text-blue-500" />
      menu (dans <code class="font-mono">/src/App.vue</code>)
    </h4>


    <ul class=" text-center mt-6">
      <li class=" mb-10">
        <router-link class=" text-white bg-blue-500 p-3 rounded-2xl hover:bg-blue-400  " to="/">
          lien vers
          <code class="font-mono">/src/pages/index.vue</code>
        </router-link>
      </li>

      <li class=" mb-10">
        
        <router-link class=" text-white bg-blue-500 p-3 rounded-2xl hover:bg-blue-400 mb-4 " to="/simple">
          lien vers Page Simple
          
        </router-link>
    
      </li>

      <li class=" mb-10">
        <router-link class=" text-white bg-blue-500 p-3 rounded-2xl hover:bg-blue-400 mb-4 " to="/liste">
          lien vers Page Liste
        </router-link>
      </li>
      
      <li class=" mb-10">
        <router-link class=" text-white bg-blue-500 p-3 rounded-2xl hover:bg-blue-400 mb-4 " to="/liste-fetch">
          lien vers Page Liste Fetch
        </router-link>
      </li>

      <li class=" mb-10">

      <router-link class=" text-white bg-blue-500 p-3 rounded-2xl hover:bg-blue-400 mb-4 " to="/edit/new">
          lien vers la page new 
          
        </router-link>
        </li>


        
      <li class=" mb-10">

<router-link class=" text-white bg-blue-500 p-3 rounded-2xl hover:bg-blue-400 mb-4 " to="/liste-supabase">
    lien vers la page Supabase 
    
  </router-link>
  </li>



  <li class=" mb-10">

<router-link class=" text-white bg-blue-500 p-3 rounded-2xl hover:bg-blue-400 mb-4 " to="/authentif">
    lien vers la page Authentification 
    
  </router-link>
  </li>

        <li class=" mb-10">

<router-link class=" text-white bg-blue-500 p-3 rounded-2xl hover:bg-blue-400 mb-4 " to="/offre/">
    lien vers la page offre nbr 
    
  </router-link>
  </li>

    </ul>
  </nav>

  <!-- Affiche les pages -->
  <Suspense> <router-view class="m-2 border-2 p-2" /></Suspense>
</template>

<script setup lang="ts">
import { Bars3Icon } from '@heroicons/vue/20/solid'
</script>
