<script setup>
import { onMounted } from 'vue'
import { gsap } from 'gsap'

onMounted(() => {
  // GSAP va automatiquement détecter TOUS les éléments avec la classe '.animated-title'
  gsap.from('.animated-title', {
    duration: 1,
    y: 30,
    opacity: 0,
    ease: 'power3.out',
    // C'EST ICI QUE LA MAGIE OPÈRE :
    stagger: 0.2, // 0.2 seconde de délai entre le H1 et le P
    delay: 0.2
  })
})
</script>

<template>
  <div class="page">
    <h1 class="animated-title">Découvrez notre univers ✨</h1>
    <p class="animated-title">Une formation accélérée et sur mesure avec Vue.js et GSAP.</p>
  </div>
</template>

<style scoped>
.page { padding: var(--space-lg); }
h1 { font-size: var(--font-lg); color: var(--primary-color); margin-bottom: var(--space-sm); }
p { font-size: var(--font-md); color: #666; }
</style>