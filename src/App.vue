<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header class="navbar">
    <nav>
      <RouterLink to="/" class="nav-link">Accueil</RouterLink> | 
      <RouterLink to="/about" class="nav-link">À Propos</RouterLink>
    </nav>
  </header>

  <main>
    <RouterView />
  </main>
</template>

<style scoped>
  .navbar {
    background-color: var(--primary-color);
    padding: var(--space-md);
    text-align: center;
  }
  .nav-link {
    color: white;
    text-decoration: none;
    margin: 0 var(--space-sm);
    font-size: var(--font-md);
  }
  /* Style généré automatiquement par Vue pour le lien de la page active ! */
  .router-link-active {
    color: var(--accent-color);
    font-weight: bold;
  }
</style>