<script setup>
import { ref } from 'vue'
import MyButton from './MyButton.vue'
import Modal from './Modal.vue'

const isModalOpen = ref(false)

const openModal = () => { isModalOpen.value = true }
const closeModal = () => { isModalOpen.value = false }
</script>

<template>
  <div class="profile-card">
    <img src="https://picsum.photos/300" alt="Avatar" class="avatar" />
    <h2>John Doe</h2>
    <p>Cliquez sur le bouton pour voir l'effet et la modale.</p>
    
    <MyButton @clic-bouton="openModal" />
  </div>

  <Modal v-if="isModalOpen" @close="closeModal" />
</template>

<style scoped>
.profile-card {
  background: white;
  padding: var(--space-lg);
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  text-align: center;
  max-width: 250px;
}
.avatar { border-radius: 50%; margin-bottom: var(--space-md); }
h2 { color: var(--primary-color); margin-bottom: var(--space-sm); }
</style>