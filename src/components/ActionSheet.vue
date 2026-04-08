<script setup>
defineProps(['isOpen'])
defineEmits(['close'])
</script>

<template>
  <Transition name="slide">
    <div v-if="isOpen" class="sheet-overlay" @click.self="$emit('close')">
      <div class="sheet-content">
        <div class="handle"></div>
        <slot></slot>
        <button class="close-btn" @click="$emit('close')">إغلاق</button>
      </div>
    </div>
  </Transition>
</template>

<style scoped>
.sheet-overlay {
  position: fixed; top: 0; left: 0; right: 0; bottom: 0;
  background: rgba(0,0,0,0.4);
  z-index: 1000;
  display: flex; align-items: flex-end;
}
.sheet-content {
  background: white;
  width: 100%;
  padding: 20px;
  border-radius: 24px 24px 0 0;
  text-align: center;
}
.handle {
  width: 40px; height: 4px;
  background: #ddd;
  margin: 0 auto 20px;
  border-radius: 2px;
}
.close-btn {
  width: 100%; padding: 12px;
  background: #f5f5f5;
  border: none; border-radius: 12px;
  margin-top: 20px;
}
/* Animation */
.slide-enter-active, .slide-leave-active { transition: all 0.3s ease; }
.slide-enter-from, .slide-leave-to { transform: translateY(100%); opacity: 0; }
</style>
