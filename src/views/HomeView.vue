<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import UserProfile from '../components/UserProfile.vue'

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  gsap.from('.second-card', {
    scrollTrigger: {
      trigger: '.second-card',
      start: 'top 80%',       // Déclenche l'apparition quand le haut de la carte est à 80% du bas de l'écran
      end: 'top 30%',         // Optionnel : définit une zone de fin
      
      // LA MAGIE EST ICI :
      // 1. play (en descendant) | 2. reverse (en remontant après avoir dépassé) 
      // 3. play (en redescendant) | 4. reverse (en remontant tout en haut)
      toggleActions: 'play reverse play reverse' 
    },
    duration: 0.8,
    scale: 0.5,
    opacity: 0,
    ease: 'back.out(1.5)' // Notre petit effet de rebond
  })
})
</script>

<template>
  <div class="page">
    <h1>🏠 Page d'Accueil</h1>
    
    <div class="spacer">Défilez vers le bas pour voir la magie... ↓</div>
    
    <div class="profile-container">
      <UserProfile />
      
      <div class="second-card">
        <UserProfile />
      </div>
    </div>
  </div>
</template>

<style scoped>
.page { padding: var(--space-lg); }
.spacer {
  height: 80vh; /* Crée un grand espace vide pour forcer le scroll */
  display: flex;
  align-items: center;
  justify-content: center;
  color: #888;
  font-style: italic;
}
.profile-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--space-lg);
  margin-top: var(--space-lg);
}
</style>