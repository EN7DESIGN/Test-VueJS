<script setup>
import { ref } from 'vue'

const emit = defineEmits(['clic-bouton'])
const estActive = ref(false)

const gererClic = () => {
  // 1. On lance immédiatement l'animation CSS de scale (0.8)
  estActive.value = true
  
  // 2. À 400ms, le bouton reprend sa taille normale en arrière-plan
  setTimeout(() => {
    estActive.value = false
  }, 300)

  // 3. On attend 450ms (le bouton est bien rétréci), puis on envoie le signal pour ouvrir la modale
  setTimeout(() => {
    emit('clic-bouton')
  }, 500)
}
</script>

<template>
  <button 
    @click="gererClic" 
    class="custom-btn" 
    :class="{ 'click-effect': estActive }"
  >
    Suivre
  </button>
</template>

<style scoped>
.custom-btn {
  background-color: var(--primary-color);
  color: white;
  padding: var(--space-sm) var(--space-md);
  font-size: var(--font-sm);
  border: none;
  border-radius: 20px;
  cursor: pointer;
  /* On ajoute une transition pour que l'effet scale soit fluide */
  transition: transform 0.1s ease-in-out;
}

/* L'effet au clic : scale à 0.8 */
.custom-btn.click-effect {
  transform: scale(0.8);
}
</style>