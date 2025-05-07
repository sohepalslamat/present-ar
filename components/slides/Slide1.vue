<template>
  <div class="slide">
    <div class="decorative-element" style="top: -100px; right: -80px;"></div>
    <div class="decorative-element" style="bottom: -150px; left: -100px;"></div>
    
    <div class="content-overlay text-white">
      <h1 class="title"><span class="blue-accent">برنامج</span> الأرشفة الإلكتروني</h1>
      <p class="subtitle">تأمين وحفظ واسترجاع الملفات والوثائق إلكترونياً</p>
      
      <div class="info-box">
        <div class="info-item">
          <i class="fas fa-calendar-alt blue-accent fa-lg"></i>
          <span>المدة: يومان تدريبيان (8 ساعات تدريبية)</span>
        </div>
        <div class="info-item">
          <i class="fas fa-bullseye blue-accent fa-lg"></i>
          <span>الهدف العام: تنمية معارف ومهارات المشاركين في مجال الأرشيف الإلكتروني</span>
        </div>
        <div class="info-item">
          <i class="fas fa-users blue-accent fa-lg"></i>
          <span>الفئات المستهدفة: أخصائيو المكتبات والمعلومات، العاملون في المكتبات ومراكز المعلومات</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Add any component logic here if needed
</script>

<style scoped>
.slide {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
  background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.7)), url('https://fekrait.com/uploads/topics/16687917262531.jpg');
  background-size: cover;
  background-position: center;
  font-family: 'Tajawal', sans-serif;
  direction: rtl;
}

.content-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 2rem;
}

.title {
  font-size: 5rem;
  font-weight: 900;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.8);
  margin-bottom: 1.5rem;
  line-height: 1.2;
}

.subtitle {
  font-size: 2.2rem;
  font-weight: 700;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.info-box {
  background-color: rgba(255, 255, 255, 0.15);
  -webkit-backdrop-filter: blur(10px);
  backdrop-filter: blur(10px);
  border-radius: 15px;
  padding: 1.5rem 2.5rem;
  margin-top: 1.5rem;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.info-item {
  display: flex;
  align-items: center;
  margin-bottom: 0.8rem;
  font-size: 1.3rem;
}

.info-item i {
  margin-left: 12px;
}

.blue-accent {
  color: #4da6ff;
}

.decorative-element {
  position: absolute;
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: linear-gradient(135deg, rgba(77, 166, 255, 0.1), rgba(77, 166, 255, 0.05));
  border: 1px solid rgba(77, 166, 255, 0.2);
  z-index: -1;
}
</style> 