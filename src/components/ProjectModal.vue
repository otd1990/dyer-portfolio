<!-- Modal.vue -->
<template>
  <section class="modal">
    <article class="modal-container">
      <div class="modal-header">
        <h3 class="modal-title">{{ modalContent.name }}</h3>
        <div class="modal-controls">
          <button
            class="modal-control"
            @click="() => $emit('minimiseModal', modalContent)"
          >
            -
          </button>
          <button class="modal-control" @click="$emit('closeModal')">X</button>
        </div>
      </div>
      <aside class="modal-content">
        <button @click="$emit('closeModal')">Close Modal</button>
      </aside>
    </article>
  </section>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  modalContent: {
    type: Object,
    default: null,
  },
});
</script>

<style scoped>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-container {
  background: #fff;
  border-radius: 8px;
  max-width: 25rem;
  width: 100%;

  display: flex;
  flex-direction: column;
}
.modal-content {
  padding: 20px;
}

.modal-header {
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
  height: 2rem;
  padding: 0.5rem 0.75rem;
  display: flex;
  align-items: center;
  justify-content: space-between;

  background-color: #164863;
  color: #fff;
}

.modal-control {
  border: 1px solid #fff;
  border-radius: 4px;
  color: #fff;
  background-color: transparent;
  width: 1.25rem;
  height: 1.25rem;
}

.modal-control + .modal-control {
  margin-left: 0.5rem;
}
</style>
