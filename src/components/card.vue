<template>
  <figure class="m-4">
    <img class="w-full rounded-t-lg" v-bind:src="image" alt="" />
    <figcaption
      class="relative flex flex-col rounded-b-lg border-2 border-t-0 px-5 py-7"
    >
      <h3 class="text-2xl text-gray-900">{{ nom }}</h3>
      <address class="not-italic text-gray-500">{{ adresse }}</address>
      <div class="order-first flex items-center">
        <div class="text-2xl text-indigo-500">
          ${{ prix.toLocaleString("en-US") }}
        </div>
        <div class="text-gray-500">/mois</div>
      </div>
      <hr class="my-2 border-t-2 border-indigo-100" />
      <div class="flex justify-between text-sm">
        <div><bed class="inline-block align-top" /> {{ nbrChambres}}</div>
        <div><bath class="inline-block align-top" /> {{ nbrSDB }}</div>
        <div><size class="inline-block align-top" /> {{ surface }}</div>
      </div>
      <div
        class="
          absolute
          top-7
          right-4
          grid
          h-12
          w-12
          place-items-center
          rounded-full
          border-2 border-indigo-100
        "
      >
        <heart :class="{ 'fill-red-400': favori }" />
      </div>
    </figcaption>
  </figure>
</template>

<script setup lang="ts">

import bed from "./icones/bed.vue";
import bath from "./icones/bath.vue";
import size from "./icones/size.vue";
import heart from "./icones/hearth.vue";
defineProps ({
    prix: {
      type: Number,
      default: 2700,
    },
    favori: {
      type: Boolean,
      default: false,
    },
    nom: {
      type: String,
      default: "Beverly Springfield",
    },
    adresse: {
      type: String,
      default: "2821 Lake Sevilla, Palm Harbor, TX",
    },
    image: {
      type: String,
    },
    nbrSDB: {
      type: String,
      default: "2 Bathrooms",
    },
    surface: {
      type: String,
      default: "6x7.5 m²",
    },
    nbrChambres: {
      type: String,
      default: "1 lit",
    }
});
</script>