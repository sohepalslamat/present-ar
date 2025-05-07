<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle" style="width: 500px; height: 500px; top: -200px; left: -200px;"></div>
    <div class="decorative-circle" style="width: 400px; height: 400px; bottom: -150px; right: -150px;"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">التحول الرقمي للأرشيف</h1>
      
      <div class="stages-container">
        <!-- Planning Stage -->
        <div class="stage-card">
          <div class="stage-number">1</div>
          <h3 class="stage-title">التخطيط</h3>
          <ul class="stage-list">
            <li class="stage-item">
              <i class="fas fa-clipboard-list stage-icon"></i>
              <span class="stage-text">تقييم احتياجات المؤسسة</span>
            </li>
            <li class="stage-item">
              <i class="fas fa-project-diagram stage-icon"></i>
              <span class="stage-text">تحديد نطاق المشروع</span>
            </li>
            <li class="stage-item">
              <i class="fas fa-tasks stage-icon"></i>
              <span class="stage-text">وضع معايير الأولوية للوثائق</span>
            </li>
            <li class="stage-item">
              <i class="fas fa-coins stage-icon"></i>
              <span class="stage-text">تخصيص الميزانية والموارد</span>
            </li>
          </ul>
        </div>
        
        <!-- Implementation Stage -->
        <div class="stage-card">
          <div class="stage-number">2</div>
          <h3 class="stage-title">التنفيذ</h3>
          <ul class="stage-list">
            <li class="stage-item">
              <i class="fas fa-desktop stage-icon"></i>
              <span class="stage-text">تهيئة البنية التقنية</span>
            </li>
            <li class="stage-item">
              <i class="fa-regular fa-image stage-icon"></i>
              <span class="stage-text">رقمنة الوثائق الورقية</span>
            </li>
            <li class="stage-item">
              <i class="fas fa-tags stage-icon"></i>
              <span class="stage-text">إنشاء نظام التصنيف والفهرسة</span>
            </li>
            <li class="stage-item">
              <i class="fas fa-shield-alt stage-icon"></i>
              <span class="stage-text">ضبط إعدادات الأمان والوصول</span>
            </li>
          </ul>
        </div>
        
        <!-- Change Management Stage -->
        <div class="stage-card">
          <div class="stage-number">3</div>
          <h3 class="stage-title">إدارة التغيير</h3>
          <ul class="stage-list">
            <li class="stage-item">
              <i class="fas fa-user-graduate stage-icon"></i>
              <span class="stage-text">تدريب الموظفين</span>
            </li>
            <li class="stage-item">
              <i class="fas fa-book stage-icon"></i>
              <span class="stage-text">إعداد أدلة المستخدم</span>
            </li>
            <li class="stage-item">
              <i class="fas fa-chart-line stage-icon"></i>
              <span class="stage-text">قياس مؤشرات الأداء</span>
            </li>
            <li class="stage-item">
              <i class="fas fa-sync stage-icon"></i>
              <span class="stage-text">التحسين المستمر للعمليات</span>
            </li>
          </ul>
        </div>
      </div>
      
      <!-- Digitization Technologies -->
      <div class="digitization-tech">
        <h3 class="tech-title">تقنيات الرقمنة الحديثة</h3>
        <div class="tech-grid">
          <div class="tech-item">
            <div class="tech-icon">
              <i class="fas fa-file-alt"></i>
            </div>
            <span class="tech-text">تقنية التعرف الضوئي على الحروف (OCR)</span>
          </div>
          <div class="tech-item">
            <div class="tech-icon">
              <i class="fas fa-pen-fancy"></i>
            </div>
            <span class="tech-text">التعرف على الكتابة اليدوية (ICR)</span>
          </div>
          <div class="tech-item">
            <div class="tech-icon">
              <i class="fas fa-barcode"></i>
            </div>
            <span class="tech-text">أنظمة الباركود والترميز التلقائي</span>
          </div>
          <div class="tech-item">
            <div class="tech-icon">
              <i class="fas fa-robot"></i>
            </div>
            <span class="tech-text">الأتمتة الروبوتية للعمليات (RPA)</span>
          </div>
          <div class="tech-item">
            <div class="tech-icon">
              <i class="fas fa-brain"></i>
            </div>
            <span class="tech-text">تصنيف الوثائق بالذكاء الاصطناعي</span>
          </div>
          <div class="tech-item">
            <div class="tech-icon">
              <i class="fas fa-cloud-upload-alt"></i>
            </div>
            <span class="tech-text">حلول الرقمنة السحابية</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

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
  padding: 1vh 3vw;
}

.slide-content {
  position: relative;
  z-index: 2;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 1vh;
}

.slide-title {
  font-size: min(2.5rem, 4.5vw);
  font-weight: bold;
  margin: 1vh 0;
  text-align: center;
  color: #ffffff;
  position: relative;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

.slide-title:after {
  content: "";
  display: block;
  width: 60px;
  height: 3px;
  background: #4da6ff;
  margin: 0.5vh auto 0;
  border-radius: 2px;
}

.stages-container {
  display: flex;
  justify-content: space-between;
  gap: 1.5vw;
  margin: 1vh 0;
  flex: 0.5;
}

.stage-card {
  flex: 1;
  background: rgba(255, 255, 255, 0.08);
  border-radius: 15px;
  padding: 1.5vh 1.5vw;
  position: relative;
  text-align: center;
  transition: all 0.3s ease;
}

.stage-card:hover {
  transform: translateY(-5px);
  background: rgba(77, 166, 255, 0.15);
}

.stage-card:before {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  width: 100%;
  height: 4px;
  background: #4da6ff;
  border-radius: 15px 15px 0 0;
}

.stage-number {
  width: 40px;
  height: 40px;
  background: #4da6ff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  font-weight: bold;
  margin: 0 auto 1vh;
}

.stage-title {
  font-size: min(1.5em, 3vw);
  font-weight: bold;
  color: #4da6ff;
  margin-bottom: 1vh;
}

.stage-list {
  list-style: none;
  padding: 0;
  text-align: right;
}

.stage-item {
  display: flex;
  align-items: flex-start;
  margin-bottom: 0.8vh;
  text-align: right;
}

.stage-icon {
  color: #4da6ff;
  margin-left: 12px;
  margin-top: 3px;
  flex-shrink: 0;
  font-size: 1.4em;
}

.stage-text {
  color: #e0e0e0;
  font-size: min(1.1em, 2.2vw);
  line-height: 1.3;
  text-align: right;
}

.digitization-tech {
  margin-top: 1vh;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 15px;
  padding: 1.5vh 1.5vw;
  flex: 0.5;
}

.tech-title {
  font-size: min(1.8em, 3.5vw);
  color: #4da6ff;
  text-align: center;
  margin-bottom: 1.5vh;
  font-weight: bold;
}

.tech-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1vh 1vw;
}

.tech-item {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 10px;
  padding: 1vh 1vw;
  display: flex;
  align-items: center;
  border-right: 3px solid #4da6ff;
}

.tech-icon {
  width: 40px;
  height: 40px;
  background: rgba(77, 166, 255, 0.2);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 1vw;
  color: #4da6ff;
  font-size: 1.2em;
}

.tech-text {
  font-size: min(1em, 2vw);
  color: #e0e0e0;
}

.decorative-circle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(77, 166, 255, 0.1) 0%, rgba(77, 166, 255, 0) 70%);
  z-index: 1;
  opacity: 0.3;
}

@media (max-width: 768px) {
  .stages-container {
    flex-direction: column;
    gap: 1vh;
  }
  
  .tech-grid {
    grid-template-columns: 1fr;
  }
  
  .stage-card {
    width: 100%;
  }
  
  .digitization-tech {
    margin-top: 1vh;
  }
}
</style> 