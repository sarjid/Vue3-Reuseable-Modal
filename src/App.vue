<script setup>
import { ref } from "vue";
import Modal from "./components/Modal.vue";
const isActiveModal = ref(false);

const toggleModal = () => {
  isActiveModal.value = !isActiveModal.value;
};
</script>

<template>
  <div class="flex items-center justify-center h-full">
    <button
      class="py-2 mt-5 px-4 bg-blue-500 text-white rounded hover:bg-blue-700"
      @click="toggleModal"
    >
      Show Modal
    </button>

    <Modal :modalStatus="isActiveModal" @close="toggleModal">
      <template #content>
        <div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
          <label>Name</label>
          <input type="text" class="w-full bg-gray-100 p-2 mt-2 mb-3" />
          <label>Url</label>
          <input type="text" class="w-full bg-gray-100 p-2 mt-2 mb-3" />
        </div>
      </template>
    </Modal>
  </div>
</template>

<style scoped></style>
