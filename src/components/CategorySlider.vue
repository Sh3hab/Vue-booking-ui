<script setup>
import { ref } from 'vue'
const activeId = ref(1)
const cats = [
  { id: 1, name: 'شاليهات', icon: 'fa-vihara' },
  { id: 2, name: 'فنادق', icon: 'fa-hotel' },
  { id: 3, name: 'مزارع', icon: 'fa-leaf' },
  { id: 4, name: 'طيرمانات', icon: 'fa-gopuram' },
  { id: 5, name: 'منتزهات', icon: 'fa-tree' }
]
</script>

<template>
  <div class="slider-container">
    <div v-for="cat in cats" :key="cat.id" 
         :class="['cat-card', { active: activeId === cat.id }]"
         @click="activeId = cat.id">
      <i :class="['fa-solid', cat.icon]"></i>
      <span>{{ cat.name }}</span>
    </div>
  </div>
</template>

<style scoped>
.slider-container {
  display: flex; gap: 15px; overflow-x: auto; padding: 10px 0;
  scrollbar-width: none;
}
.cat-card {
  min-width: 75px; display: flex; flex-direction: column; align-items: center;
  gap: 8px; color: #666; transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  cursor: pointer; padding-bottom: 8px;
}
.cat-card i { font-size: 1.4rem; }
.cat-card span { font-size: 0.8rem; font-weight: 600; }
.cat-card.active { color: #000; border-bottom: 2.5px solid #000; transform: translateY(-2px); }
</style>
