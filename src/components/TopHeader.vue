<template>
  <header class="header-container">
    <div class="user-section">
      <div class="avatar-wrapper">
        <i class="fa-solid fa-user"></i>
      </div>
      <div class="user-text">
        <p class="greeting">مرحباً بك، <span>شهاب</span></p>
        <div class="location-picker">
          <span class="city">صنعاء</span>
          <i class="fa-solid fa-chevron-down"></i>
        </div>
      </div>
    </div>
    <div class="action-icons">
      <div class="icon-circle whatsapp"><i class="fa-brands fa-whatsapp"></i></div>
      <div class="icon-circle"><i class="fa-solid fa-bell"></i></div>
    </div>
  </header>
</template>

<style scoped>
.header-container {
  display: flex; justify-content: space-between; align-items: center;
  padding: 10px 0; margin-bottom: 20px;
}
.user-section { display: flex; align-items: center; gap: 12px; }
.avatar-wrapper {
  width: 45px; height: 45px; background: #e0e0e0;
  border-radius: 50%; display: flex; align-items: center; justify-content: center;
  color: #777; font-size: 1.2rem;
}
.greeting { margin: 0; font-size: 0.85rem; color: #888; }
.greeting span { color: #333; font-weight: bold; }
.location-picker { display: flex; align-items: center; gap: 5px; color: #14b8a6; font-weight: bold; font-size: 0.9rem; }

.action-icons { display: flex; gap: 10px; }
.icon-circle {
  width: 38px; height: 38px; background: white; border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  box-shadow: 0 2px 8px rgba(0,0,0,0.05); color: #555;
}
.whatsapp { color: #25D366; }
</style>
