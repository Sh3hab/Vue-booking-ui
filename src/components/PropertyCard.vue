<template>
  <div class="card-wrapper">
    <div class="image-layout">
      <div class="main-frame">
        <div class="placeholder-img"><i class="fa-solid fa-image"></i></div>
      </div>
      <div class="side-frames">
        <div class="sub-frame"></div>
        <div class="sub-frame"></div>
      </div>
    </div>
    
    <div class="info-box">
      <div class="title-line">
        <i class="fa-solid fa-circle-check verified"></i>
        <h3>شالية لافندر</h3>
      </div>
      <div class="loc-line">
        <i class="fa-solid fa-location-dot"></i>
        <p>صنعاء، خط المطار، دارس، جوار المجلس المحلي امام مستشفى المجد التخصصي</p>
      </div>
      <div class="rating-badge">
        <i class="fa-solid fa-star"></i>
        <span>4.0</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card-wrapper {
  background: white; border-radius: 28px; overflow: hidden; margin-bottom: 25px;
  box-shadow: 0 8px 20px rgba(0,0,0,0.04);
  animation: fadeInUp 0.6s ease backwards;
}

.image-layout { display: grid; grid-template-columns: 1.8fr 1fr; gap: 6px; height: 210px; padding: 6px; }
.main-frame { background: #f0f0f0; border-radius: 6px 22px 22px 6px; display: flex; align-items: center; justify-content: center; font-size: 2rem; color: #ccc; }
.side-frames { display: grid; grid-template-rows: 1fr 1fr; gap: 6px; }
.sub-frame { background: #e5e5e5; border-radius: 22px; }
.sub-frame:first-child { border-radius: 22px 6px 6px 6px; }
.sub-frame:last-child { border-radius:6px 6px 6px 22px; }

.info-box { padding: 18px; position: relative; }
.title-line { display: flex; align-items: center; gap: 8px; margin-bottom: 10px; }
.title-line h3 { margin: 0; font-size: 1.15rem; font-weight: 800; }
.verified { color: #14b8a6; font-size: 1.1rem; }

.loc-line { display: flex; gap: 8px; color: #777; line-height: 1.5; }
.loc-line p { margin: 0; font-size: 0.82rem; flex: 1; }
.loc-line i { margin-top: 3px; font-size: 0.9rem; }

.rating-badge {
  position: absolute; left: 18px; top: 18px;
  background: #FFF9E6; color: #FFB800; padding: 6px 12px;
  border-radius: 14px; display: flex; align-items: center; gap: 5px; font-weight: bold;
}

@keyframes fadeInUp {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}
</style>
