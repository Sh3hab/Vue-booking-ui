<template>
  <div class="profile-container">
    <div class="header-actions">
      <div class="top-icons">
        <i class="fa-solid fa-bell"></i>
        <i class="fa-brands fa-whatsapp whatsapp-icon"></i>
      </div>
      <h2 class="page-title">الحساب</h2>
    </div>

    <div class="user-card">
      <i class="fa-solid fa-right-from-bracket logout-icon"></i>
      <div class="user-details">
        <span class="user-name">شهاب بندر</span>
        <div class="avatar-circle">
          <i class="fa-solid fa-user"></i>
        </div>
      </div>
    </div>

    <div class="settings-list">
      <div class="setting-item">
        <span class="label-gray">المدينة</span>
        <div class="item-content">
          <span class="value-text">صنعاء</span>
          <i class="fa-solid fa-location-dot icon-teal"></i>
        </div>
      </div>

      <div class="setting-item">
        <span class="label-gray">عملة العرض</span>
        <div class="item-content">
          <span class="value-text">ريال قديم</span>
          <i class="fa-solid fa-money-bill-transfer icon-teal"></i>
        </div>
      </div>

      <div class="special-card">
        <i class="fa-solid fa-arrow-up-right-from-square"></i>
        <div class="item-content">
          <span class="special-text">إضافة المنشأة الخاصة بك</span>
          <i class="fa-solid fa-house-medical"></i>
        </div>
      </div>

      <div v-for="(link, index) in links" :key="index" class="link-item">
        <i class="fa-solid fa-chevron-left arrow-icon"></i>
        <div class="item-content">
          <span class="link-text">{{ link.text }}</span>
          <i :class="['fa-solid', link.icon, 'icon-teal']"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const links = [
  { text: 'المفضلة', icon: 'fa-heart' },
  { text: 'الأعدادات', icon: 'fa-gear' },
  { text: 'سياسة الخصوصية', icon: 'fa-shield-halved' },
  { text: 'تقديم شكوى أو مقترح', icon: 'fa-comment-dots' },
  { text: 'قنوات التواصل والدعم الفني', icon: 'fa-headset' },
]
</script>

<style scoped>
.profile-container { padding: 20px; background: #f8f9fa; min-height: 100vh; direction: rtl; }

.header-actions { display: flex; justify-content: space-between; align-items: center; margin-bottom: 25px; }
.top-icons { display: flex; gap: 15px; font-size: 1.2rem; color: #555; }
.whatsapp-icon { color: #25D366; }
.page-title { margin: 0; font-size: 1.3rem; font-weight: 800; }

.user-card { 
  background: white; border-radius: 20px; padding: 15px; 
  display: flex; justify-content: space-between; align-items: center;
  box-shadow: 0 2px 10px rgba(0,0,0,0.02); margin-bottom: 15px;
}
.logout-icon { color: #bbb; cursor: pointer; }
.user-details { display: flex; align-items: center; gap: 15px; }
.user-name { font-weight: bold; font-size: 1.1rem; }
.avatar-circle { 
  width: 50px; height: 50px; background: #eef2f3; 
  border-radius: 50%; display: flex; align-items: center; justify-content: center; color: #cbd5e0;
}

.setting-item, .link-item, .special-card {
  background: white; border-radius: 20px; padding: 18px;
  display: flex; justify-content: space-between; align-items: center;
  margin-bottom: 12px; box-shadow: 0 2px 8px rgba(0,0,0,0.02);
}

.special-card { background: #f0fdfa; border: 1.5px solid #99f6e4; color: #0d9488; }
.special-text { font-weight: bold; }

.item-content { display: flex; align-items: center; gap: 12px; }
.icon-teal { color: #14b8a6; font-size: 1.1rem; width: 20px; text-align: center; }
.label-gray { color: #94a3b8; font-size: 0.9rem; }
.value-text { font-weight: 600; color: #334155; }
.link-text { font-weight: 600; color: #1e293b; }
.arrow-icon { color: #cbd5e0; font-size: 0.8rem; }
</style>
