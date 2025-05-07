<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle" style="width: 500px; height: 500px; top: -200px; left: -200px;"></div>
    <div class="decorative-circle" style="width: 400px; height: 400px; bottom: -100px; right: -100px;"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">أهمية الأرشيف الإلكتروني</h1>
      
      <div class="importance-grid">
        <!-- Main importance item -->
        <div class="importance-item main-item">
          <div class="item-icon">
            <i class="fas fa-lightbulb fa-2x text-white"></i>
          </div>
          <div>
            <h3 class="importance-title">الأهمية في المؤسسات</h3>
            <ul class="benefit-list">
              <li class="benefit-item">
                <i class="fas fa-check-circle bullet-icon"></i>
                <span class="benefit-text">تحسين الكفاءة التشغيلية وسرعة الوصول للمعلومات</span>
              </li>
              <li class="benefit-item">
                <i class="fas fa-check-circle bullet-icon"></i>
                <span class="benefit-text">تقليل التكاليف المرتبطة بالتخزين المادي للوثائق</span>
              </li>
              <li class="benefit-item">
                <i class="fas fa-check-circle bullet-icon"></i>
                <span class="benefit-text">تسهيل المشاركة والتعاون بين فرق العمل المختلفة</span>
              </li>
            </ul>
          </div>
        </div>
        
        <!-- Value item -->
        <div class="importance-item">
          <h3 class="importance-title">القيمة القانونية والإدارية</h3>
          <ul class="benefit-list">
            <li class="benefit-item">
              <i class="fas fa-gavel bullet-icon"></i>
              <span class="benefit-text">الحجية القانونية للوثائق الإلكترونية</span>
            </li>
            <li class="benefit-item">
              <i class="fas fa-history bullet-icon"></i>
              <span class="benefit-text">حفظ الذاكرة المؤسسية والتاريخ الإداري</span>
            </li>
            <li class="benefit-item">
              <i class="fas fa-clipboard-check bullet-icon"></i>
              <span class="benefit-text">المساعدة في التدقيق والمراجعة والامتثال</span>
            </li>
            <li class="benefit-item">
              <i class="fas fa-chart-line bullet-icon"></i>
              <span class="benefit-text">دعم اتخاذ القرارات الاستراتيجية</span>
            </li>
          </ul>
        </div>
        
        <!-- Challenges item -->
        <div class="importance-item">
          <h3 class="importance-title">التحديات المعاصرة</h3>
          <div class="challenge-grid">
            <div class="challenge-item">
              <div class="challenge-icon">
                <i class="fas fa-shield-alt"></i>
              </div>
              <span class="challenge-text">الأمن السيبراني وحماية البيانات</span>
            </div>
            <div class="challenge-item">
              <div class="challenge-icon">
                <i class="fas fa-balance-scale"></i>
              </div>
              <span class="challenge-text">الامتثال للتشريعات والأنظمة</span>
            </div>
            <div class="challenge-item">
              <div class="challenge-icon">
                <i class="fas fa-database"></i>
              </div>
              <span class="challenge-text">إدارة حجم البيانات المتزايد</span>
            </div>
            <div class="challenge-item">
              <div class="challenge-icon">
                <i class="fas fa-clock"></i>
              </div>
              <span class="challenge-text">تقادم التقنيات وديمومة الحفظ</span>
            </div>
            <div class="challenge-item">
              <div class="challenge-icon">
                <i class="fas fa-brain"></i>
              </div>
              <span class="challenge-text">مواكبة التقنيات الذكية</span>
            </div>
            <div class="challenge-item">
              <div class="challenge-icon">
                <i class="fas fa-user-lock"></i>
              </div>
              <span class="challenge-text">ضمان خصوصية وسرية المعلومات</span>
            </div>
          </div>
        </div>
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

.importance-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2vh 2vw;
  margin-top: 2vh;
  flex: 1;
  max-width: 1400px;
  margin: 0 auto;
  width: 100%;
}

.importance-item {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 15px;
  padding: 2vh 2vw;
  position: relative;
  transition: all 0.3s ease;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.importance-item:hover {
  background: rgba(77, 166, 255, 0.15);
  transform: translateY(-5px);
}

.importance-item.main-item {
  grid-column: span 2;
  display: flex;
  flex-direction: row;
  align-items: flex-start;
}

.item-icon {
  background: linear-gradient(135deg, #3490dc, #4da6ff);
  width: min(70px, 10vw);
  height: min(70px, 10vw);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 20px;
  flex-shrink: 0;
}

.importance-title {
  font-size: min(24px, 3vw);
  font-weight: bold;
  margin-bottom: 1.5vh;
  color: #4da6ff;
}

.benefit-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.benefit-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 1vh;
}

.bullet-icon {
  color: #4da6ff;
  margin-left: 10px;
  margin-top: 5px;
  flex-shrink: 0;
  font-size: min(16px, 2.5vw);
}

.benefit-text {
  color: #e0e0e0;
  font-size: min(16px, 2.2vw);
  line-height: 1.5;
}

.challenge-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5vh 1.5vw;
  margin-top: 1.5vh;
  height: 100%;
}

.challenge-item {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  padding: 1vh 1vw;
  display: flex;
  align-items: center;
  border-right: 3px solid #ff8c4d;
  min-height: 50px;
}

.challenge-icon {
  background: rgba(255, 140, 77, 0.2);
  width: min(40px, 8vw);
  height: min(40px, 8vw);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 12px;
  color: #ff8c4d;
  flex-shrink: 0;
}

.challenge-icon i {
  font-size: min(14px, 2vw);
}

.challenge-text {
  color: #e0e0e0;
  font-size: min(14px, 2vw);
  line-height: 1.4;
}

.decorative-circle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(77, 166, 255, 0.1) 0%, rgba(77, 166, 255, 0) 70%);
  z-index: 1;
}
</style> 