<template>
  <header class="sticky top-0 bg-weather-primary shadow-lg">
    <nav class="container flex justify-between flex-col sm:flex-row items-center gap-4 text-white py-6">
      <RouterLink :to="{ name: 'home' }">
        <div class="flex items-center gap-3 flex-1">
          <i class="fa-solid fa-sun text-2xl"></i>
          <span class="text-2xl">The Local Weather</span>
        </div>
      </RouterLink>

      <div class="flex gap-3">
        <i class="fa-solid fa-circle-info text-xl hover:text-weather-secondary duration-150 cursor-pointer" @click="toggleModal"></i>
        <i class="fa-solid fa-plus text-xl hover:text-weather-secondary duration-150 cursor-pointer"></i>
      </div>
    </nav>
  </header>
  <BaseModal :modal-active="modalActive" @close-modal="toggleModal">
    <div class="text-black">
      <h1>About</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos nostrum facilis necessitatibus neque. Consectetur molestias neque ipsum eius, iusto aut!</p>
    </div>
  </BaseModal>
</template>


<script setup lang="ts">
import { ref } from '@vue/reactivity';
import { RouterLink } from 'vue-router';
import BaseModal from '../components/BaseModal.vue';

const modalActive = ref<Boolean>(false);

const toggleModal = () => {
  modalActive.value = !modalActive.value;
}

</script>
