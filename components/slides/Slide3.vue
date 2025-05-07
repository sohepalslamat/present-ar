<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle top-right"></div>
    <div class="decorative-circle bottom-left"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">الفئات المستهدفة</h1>
      
      <div class="target-groups">
        <!-- Target Group 1 -->
        <div class="target-card">
          <div class="icon-circle">
            <i class="fas fa-book-reader fa-2x text-white"></i>
          </div>
          <h3 class="target-title">أخصائيو المكتبات والمعلومات</h3>
          <p class="target-description">المتخصصون في تنظيم المعلومات والوثائق وحفظها وإدارة المكتبات الرقمية والتقليدية</p>
        </div>
        
        <!-- Target Group 2 -->
        <div class="target-card">
          <div class="icon-circle">
            <i class="fas fa-building fa-2x text-white"></i>
          </div>
          <h3 class="target-title">العاملون في المكتبات ومراكز المعلومات</h3>
          <p class="target-description">موظفو المكتبات ومراكز المعلومات في المؤسسات الحكومية والخاصة المسؤولون عن إدارة المحتوى</p>
        </div>
        
        <!-- Target Group 3 -->
        <div class="target-card">
          <div class="icon-circle">
            <i class="fas fa-database fa-2x text-white"></i>
          </div>
          <h3 class="target-title">العاملون في إدارات المعلومات والأرشيف</h3>
          <p class="target-description">متخصصو إدارة المعلومات والأرشفة والحفظ الرقمي المسؤولون عن حفظ وإتاحة الوثائق المؤسسية</p>
        </div>
        
        <!-- Target Group 4 -->
        <div class="target-card">
          <div class="icon-circle">
            <i class="fas fa-users-cog fa-2x text-white"></i>
          </div>
          <h3 class="target-title">الإداريون في الشركات والمؤسسات</h3>
          <p class="target-description">المديرون والإداريون المسؤولون عن حوكمة المعلومات واتخاذ القرارات المتعلقة بإدارة الوثائق</p>
        </div>
      </div>
      
      <div class="footer-note">
        <i class="fas fa-info-circle"></i> البرنامج مصمم لتلبية احتياجات مختلف المتخصصين في مجال إدارة المعلومات والوثائق
      </div>
    </div>
  </div>
</template>

<script setup>
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
}

.slide-title {
  font-size: 2.5rem;
  font-weight: bold;
  margin: 4vh 0;
  text-align: center;
  color: #ffffff;
  position: relative;
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

.target-groups {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 4vh 4vw;
  flex: 1;
  width: 100%;
  max-width: 1400px;
  margin: 0 auto;
  align-items: stretch;
}

.target-card {
  background-color: rgba(255, 255, 255, 0.08);
  border-radius: 15px;
  padding: 4vh 2vw;
  text-align: center;
  position: relative;
  border: 1px solid rgba(77, 166, 255, 0.2);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2vh;
}

.target-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
  background-color: rgba(77, 166, 255, 0.15);
}

.icon-circle {
  width: 70px;
  height: 70px;
  background: #4da6ff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
}

.icon-circle i {
  font-size: 1.8rem;
}

.target-title {
  font-size: 1.4rem;
  font-weight: bold;
  color: #4da6ff;
  line-height: 1.4;
}

.target-description {
  color: #e0e0e0;
  font-size: 1rem;
  line-height: 1.6;
  margin: 0;
  flex-grow: 1;
}

.decorative-circle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(77, 166, 255, 0.1) 0%, rgba(77, 166, 255, 0) 70%);
  z-index: 1;
}

.decorative-circle.top-right {
  width: 600px;
  height: 600px;
  top: -200px;
  right: -200px;
}

.decorative-circle.bottom-left {
  width: 500px;
  height: 500px;
  bottom: -200px;
  left: -200px;
}

.footer-note {
  text-align: center;
  font-size: 0.9rem;
  color: rgba(255, 255, 255, 0.5);
  margin-top: 3vh;
  padding-bottom: 2vh;
}
</style> 