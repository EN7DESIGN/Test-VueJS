<script setup>
// On définit un événement pour dire au parent quand fermer le pop-up
defineEmits(['close'])
</script>

<template>
  <div class="modal-overlay" @click="$emit('close')">
    <div class="modal-content" @click.stop>
      <h3>Détails du Profil</h3>
      <p>Voici plus d'informations sur John Doe...</p>
      <button @click="$emit('close')" class="close-btn">Fermer</button>
    </div>
  </div>
</template>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0; left: 0; width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex; justify-content: center; align-items: center;
  z-index: 1000;
}
.modal-content {
  background: white; padding: var(--space-lg);
  border-radius: 8px; text-align: center; max-width: 400px; width: 90%;
}
.close-btn {
  background: var(--primary-color); color: white;
  border: none; padding: var(--space-sm) var(--space-md);
  border-radius: 4px; cursor: pointer; margin-top: var(--space-md);
}
</style>