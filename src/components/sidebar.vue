<template>
  <div class="sidebar" style="height: 100vh; min-width: 170px;">
    <ul class="menu">
      <li v-for="(item, index) in menuItems" :key="index" :class="{ 'active': activeIndex === index }">
        <a @click="setActive(index, item)">
          {{ item }}
        </a>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { defineEmits } from 'vue'

const emit = defineEmits(['selectedModule'])
const activeIndex = ref(0);
const menuItems = ['DashBoard','Create Task']

const setActive = (index, name) => {
  activeIndex.value = index;
  emit('selectedModule', name)
  // You can also perform routing or other actions here based on the selected menu item
};
</script>