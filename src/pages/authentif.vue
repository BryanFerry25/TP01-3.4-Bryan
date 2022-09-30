<script setup lang="ts">
    import { ref } from "@vue/reactivity";
    import { supabase, user } from "@/supabase";
    
    async function signIn(data, node) {
      const { user, error } = await (nvlUtilisateur.value
        ? supabase.auth.signUp(data)
        : supabase.auth.signIn(data));
      if (error) {
        console.error(error);
        node.setErrors([error.message]);
      }
    }
    const nvlUtilisateur = ref(false);
    </script>
    <template>
      <div class=" bg-blue-200 text-center">
        <button class=" bg-red-500" v-if="user" @pointerdown="supabase.auth.signOut()">
          Se déconnecter ({{ user.email }})
        </button>
        <FormKit
        
          v-else
          type="form"
          :submit-label="nvlUtilisateur ? 'S\'inscrire' : 'Se connecter'"
          @submit="signIn"
        >
        <div class=" text-2xl mb-10">
          <FormKit name="email" label="Votre eMail" type="email" />
        </div>
        <div class=" text-2xl mb-10">
          <FormKit name="password" label="Mot de passe" type="password" />
        </div>
        <div class=" text-blue-900">
          <formKit
            label="Nouvel utilisateur ?"
            name="nvlUtilisateur"
            type="checkbox"
            v-model="nvlUtilisateur"
          />
        </div>
        </FormKit>
        
      </div>
    </template>