<template>
  <Teleport to="body">
    <Transition name="modal-outer">
      <div v-show="modalActive" class="absolute w-full bg-black bg-opacity-30 h-screen top-0 left-0 flex justify-center px-8">
        <div v-if="modalActive" class="p-4 bg-white self-start mt-32 max-w-screen-md">
          <slot />
          <button class="text-white mt-8 bg-weather-primary py-2 px-6" @click="$emit('close-modal')">Close</button>
        </div>
      </div>
    </Transition>
  </Teleport>
</template>


<script setup lang="ts">
import type { PropType } from "@vue/runtime-core";

defineEmits(['close-modal']);

defineProps({
  modalActive: {
    type: Boolean as PropType<Boolean>,
    default: false
  }
});


</script>

<style scoped>

.modal-outer-enter-active, .modal-outer-leave-active {
  transition: 300ms opacity ease;
}

.modal-outer-enter-from, .modal-outer-leave-to {
  opacity: 0;
}

.modal-outer-enter-to, .modal-outer-leave-from {
  opacity: 1;
}

</style>