<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle" style="width: 500px; height: 500px; top: -200px; right: -150px;"></div>
    <div class="decorative-circle" style="width: 400px; height: 400px; bottom: -100px; left: -150px;"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">تقنيات الحفظ والاسترجاع</h1>
      
      <div class="systems-grid">
        <!-- ECM System -->
        <div class="system-card">
          <div class="system-header">
            <div class="system-icon">
              <i class="fas fa-sitemap fa-2x text-white"></i>
            </div>
            <div>
              <h3 class="system-title">أنظمة إدارة المحتوى (ECM)</h3>
              <p class="system-subtitle">Enterprise Content Management</p>
            </div>
          </div>
          <ul class="feature-list">
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">إدارة شاملة لجميع أنواع المحتوى المؤسسي</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">التحكم في دورة حياة المستندات بالكامل</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">دعم سير العمل وإدارة العمليات التجارية</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">توفير التعاون وتبادل المحتوى بشكل آمن</span>
            </li>
          </ul>
        </div>
        
        <!-- DMS System -->
        <div class="system-card">
          <div class="system-header">
            <div class="system-icon">
              <i class="fas fa-file-archive fa-2x text-white"></i>
            </div>
            <div>
              <h3 class="system-title">أنظمة إدارة الوثائق (DMS)</h3>
              <p class="system-subtitle">Document Management Systems</p>
            </div>
          </div>
          <ul class="feature-list">
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">تتبع الإصدارات وتاريخ الوثائق</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">التصنيف متعدد المستويات والفهرسة</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">البحث الذكي والاسترجاع السريع</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">ضبط الأذونات وصلاحيات الوصول</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'

</script>

<style scoped>
.slide {
  width: 100%;
  height: 100vh;
  background: linear-gradient(135deg, #1a2a3a 0%, #0d1b2a 100%);
  color: #ffffff;
  overflow: hidden;
  position: relative;
  display: flex;
  flex-direction: column;
  padding: 2vh 4vw;
}

.slide-content {
  position: relative;
  z-index: 2;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.slide-title {
  font-size: min(2.5rem, 5vw);
  font-weight: bold;
  margin: 2vh 0;
  text-align: center;
  color: #ffffff;
  position: relative;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

.slide-title:after {
  content: "";
  display: block;
  width: 80px;
  height: 4px;
  background: #4da6ff;
  margin: 1vh auto 0;
  border-radius: 2px;
}

.systems-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2vh 3vw;
  margin: 2vh auto;
  width: 100%;
  max-width: 1400px;
}

.system-card {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 15px;
  padding: 2vh 2vw;
  height: 100%;
  transition: all 0.3s ease;
  border-bottom: 4px solid #4da6ff;
}

.system-card:hover {
  transform: translateY(-5px);
  background: rgba(77, 166, 255, 0.15);
}

.system-header {
  display: flex;
  align-items: center;
  margin-bottom: 2vh;
}

.system-icon {
  background: linear-gradient(135deg, #3490dc, #4da6ff);
  width: min(60px, 8vw);
  height: min(60px, 8vw);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 15px;
}

.system-title {
  font-size: min(24px, 3vw);
  font-weight: bold;
  color: #4da6ff;
}

.system-subtitle {
  font-size: min(16px, 2vw);
  color: #e0e0e0;
  opacity: 0.8;
}

.feature-list {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 1vh;
}

.feature-icon {
  color: #4da6ff;
  margin-left: 10px;
  margin-top: 5px;
  font-size: min(16px, 2.5vw);
}

.feature-text {
  color: #e0e0e0;
  font-size: min(16px, 2.2vw);
  line-height: 1.5;
}

.decorative-circle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(77, 166, 255, 0.1) 0%, rgba(77, 166, 255, 0) 70%);
  z-index: 1;
}
</style> 