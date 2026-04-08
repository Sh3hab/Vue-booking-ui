<script setup>
import { ref } from 'vue'
import TopHeader from './components/TopHeader.vue'
import CategorySlider from './components/CategorySlider.vue'
import PropertyCard from './components/PropertyCard.vue'
import ProfileScreen from './components/ProfileScreen.vue'

// متغير التحكم في التبويبات
const currentTab = ref('home')
</script>

<template>
  <div class="mobile-frame">
    
    <transition name="page-fade" mode="out-in">
      
      <div v-if="currentTab === 'home'" key="home">
        <TopHeader />

        <div class="search-box">
          <i class="fa-solid fa-magnifying-glass"></i>
          <input type="text" placeholder="ابحث عن منشأة.." />
        </div>

        <CategorySlider />

        <div class="list-container">
          <PropertyCard v-for="i in 3" :key="i" :style="{ animationDelay: (i * 0.1) + 's' }" />
        </div>
      </div>

      <div v-else-if="currentTab === 'profile'" key="profile">
        <ProfileScreen />
      </div>

    </transition>

    <nav class="bottom-tab-bar">
      <div class="tab-item" :class="{ active: currentTab === 'home' }" @click="currentTab = 'home'">
        <i class="fa-solid fa-house-chimney"></i>
        <span>المنشئات</span>
      </div>
      
      <div class="tab-item">
        <i class="fa-solid fa-magnifying-glass"></i>
        <span>البحث</span>
      </div>
      
      <div class="tab-item">
        <i class="fa-solid fa-calendar-check"></i>
        <span>الحجوزات</span>
      </div>
      
      <div class="tab-item" :class="{ active: currentTab === 'profile' }" @click="currentTab = 'profile'">
        <i class="fa-solid fa-circle-user"></i>
        <span>الحساب</span>
      </div>
    </nav>
  </div>
</template>

<style>
/* التنسيقات العامة */
body { 
  background: #f2f4f7; 
  direction: rtl; 
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
  margin: 0; 
  overflow-x: hidden;
}

.mobile-frame { 
  padding: 15px; 
  padding-bottom: 100px; 
}

/* شريط البحث */
.search-box {
  background: white; border-radius: 20px; padding: 15px;
  display: flex; align-items: center; gap: 12px; margin-bottom: 20px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.02);
}
.search-box i { color: #bbb; }
.search-box input { border: none; outline: none; flex: 1; font-size: 1rem; background: transparent; }

/* شريط التنقل السفلي */
.bottom-tab-bar {
  position: fixed; bottom: 0; left: 0; right: 0;
  background: white; height: 80px; display: flex; justify-content: space-around;
  align-items: center; padding-bottom: 10px;
  border-top: 1px solid #eee; z-index: 2000;
}
.tab-item { 
  display: flex; flex-direction: column; align-items: center; 
  color: #999; gap: 5px; cursor: pointer; transition: all 0.3s ease;
}
.tab-item.active { color: #14b8a6; transform: translateY(-3px); }
.tab-item i { font-size: 1.3rem; }
.tab-item span { font-size: 0.75rem; font-weight: bold; }

/* أنيميشن الانتقال السلس بين الصفحات */
.page-fade-enter-active,
.page-fade-leave-active {
  transition: all 0.3s ease;
}

.page-fade-enter-from {
  opacity: 0;
  transform: translateX(30px); /* دخول من الجنب */
}

.page-fade-leave-to {
  opacity: 0;
  transform: translateX(-30px); /* خروج للجنب الآخر */
}
</style>
