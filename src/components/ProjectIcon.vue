<!-- ProjectIcon.vue -->
<template>
  <article class="project-icon">
    <button @click="$emit('openModalIcon')">
      <img
        :src="require(`@/assets/images/${icon}`)"
        :alt="projectDesc"
        class="project-icon-image"
      />
      <aside class="project-details">
        <h2 class="project-name">{{ projectName }}</h2>
      </aside>
    </button>
  </article>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  projectName: {
    type: String,
    default: "",
  },
  projectDesc: {
    type: String,
    default: "",
  },
  icon: {
    type: String,
    default: "",
  },
});
</script>

<style scoped>
.project-icon {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.project-icon button {
  background: none;
  border: none;
  cursor: pointer;
}
.project-icon-image {
  height: 3.25rem;
  width: 3.25rem;
}

.project-name {
  font-size: 0.85rem;
  font-weight: normal;
}
.project-details {
  background-color: transparent;
  width: fit-content;
  margin-top: 0.2rem;
  padding: 0 0.25rem;
}
</style>
