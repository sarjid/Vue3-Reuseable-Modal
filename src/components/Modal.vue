<script setup>
const props = defineProps({
  modalStatus: {
    type: Boolean,
    required: true,
    default: false,
  },
});

const emit = defineEmits(["close"]);

const closeModal = () => {
  emit("close");
};
</script>

<template>
  <div
    class="fixed z-10 overflow-y-auto top-0 w-full left-0"
    v-show="modalStatus"
  >
    <div
      class="flex items-center justify-center min-height-100vh pt-4 px-4 pb-20 text-center sm:block sm:p-0"
    >
      <div class="fixed inset-0 transition-opacity" @click="closeModal">
        <div class="absolute inset-0 bg-gray-900 opacity-75" />
      </div>

      <span class="hidden sm:inline-block sm:align-middle sm:h-screen"
        >&#8203;</span
      >
      <div
        class="inline-block align-center bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full"
        role="dialog"
        aria-modal="true"
        aria-labelledby="modal-headline"
      >
        <slot name="content"></slot>
        <div class="bg-gray-200 px-4 py-3 text-right">
          <button
            type="button"
            class="py-2 px-4 bg-gray-500 text-white rounded hover:bg-gray-700 mr-2"
            @click="closeModal"
          >
            <i class="fas fa-times"></i> Cancel
          </button>
          <button
            type="button"
            class="py-2 px-4 bg-blue-500 text-white rounded hover:bg-blue-700 mr-2"
          >
            <i class="fas fa-plus"></i> Create
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
