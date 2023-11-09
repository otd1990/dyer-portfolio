<template>
  <article>
    <div class="mini-toolbar">
      <h1>{{ projectName }}</h1>
      <div class="mini-controls">
        <button class="mini-control" @click="$emit('openModal')">+</button>
        <button class="mini-control" @click="() => $emit('closeMini', miniKey)">
          {{ miniKey }}
        </button>
      </div>
    </div>
  </article>
</template>
<script setup>
import { defineProps } from "vue";

defineProps({
  projectName: {
    type: String,
    default: "",
  },
  miniKey: {
    type: Number,
    default: null,
  },
});
</script>
<style scoped>
.mini-toolbar {
  border-radius: 8px;
  height: 2rem;
  padding: 0.5rem 0.75rem;
  display: flex;
  align-items: center;
  justify-content: space-between;

  background-color: #ddf2fd;
  color: #0f0f0f;
}

.mini-controls {
  display: flex;
}

.mini-control {
  border: 1px solid #0f0f0f;
  border-radius: 4px;
  color: #0f0f0f;
  background-color: transparent;
  width: 1.25rem;
  height: 1.25rem;
  line-height: 0;
}

.mini-control + .mini-control {
  margin-left: 0.5rem;
}
</style>
