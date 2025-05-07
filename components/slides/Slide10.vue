<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle" style="width: 500px; height: 500px; top: -200px; left: -200px;"></div>
    <div class="decorative-circle" style="width: 400px; height: 400px; bottom: -150px; right: -150px;"></div>
    
    <div class="slide-content">
      <div class="coding-standards">
        <h2 class="section-title">أنظمة الترميز الدولية</h2>
        
        <div class="coding-grid">
          <!-- ISAD(G) Standard -->
          <div class="coding-item">
            <div class="coding-icon">
              <i class="fas fa-sitemap"></i>
            </div>
            <h3 class="coding-name">ISAD(G)</h3>
            <p class="coding-desc">المعيار الدولي العام للوصف الأرشيفي - يوفر إرشادات لإعداد الوصف الأرشيفي متعدد المستويات</p>
            <p class="coding-desc mt-2">يتضمن 7 عناصر أساسية للوصف: التعريف، السياق، المحتوى، شروط الوصول، المواد ذات الصلة، الملاحظات، ضبط الوصف</p>
          </div>
          
          <!-- EAD Standard -->
          <div class="coding-item">
            <div class="coding-icon">
              <i class="fas fa-code"></i>
            </div>
            <h3 class="coding-name">EAD</h3>
            <p class="coding-desc">الوصف الأرشيفي المرمز - معيار XML لترميز الأدوات المساعدة الأرشيفية</p>
            <p class="coding-desc mt-2">يسمح بالوصف متعدد المستويات للمواد الأرشيفية وتبادلها بين المؤسسات، متوافق مع ISAD(G)</p>
          </div>
          
          <!-- ISO 25964 Standard -->
          <div class="coding-item">
            <div class="coding-icon">
              <i class="fas fa-book"></i>
            </div>
            <h3 class="coding-name">ISO 25964</h3>
            <p class="coding-desc">المكانز وقابلية التشغيل البيني مع المكانز الأخرى - معيار لإنشاء وإدارة المكانز المستخدمة في استرجاع المعلومات</p>
          </div>
        </div>
      </div>

      <div class="benefits-section">
        <h2 class="section-title">فوائد تطبيق المعايير الدولية</h2>
        
        <div class="benefits-grid">
          <div class="benefit-card">
            <div class="benefit-header">
              <div class="benefit-icon">
                <i class="fas fa-sync"></i>
              </div>
              <h3 class="benefit-name">قابلية التشغيل البيني</h3>
            </div>
            <p class="benefit-desc">تبادل البيانات بين أنظمة مختلفة والتكامل السلس بين المؤسسات</p>
          </div>
          
          <div class="benefit-card">
            <div class="benefit-header">
              <div class="benefit-icon">
                <i class="fas fa-balance-scale"></i>
              </div>
              <h3 class="benefit-name">الامتثال التنظيمي</h3>
            </div>
            <p class="benefit-desc">تلبية المتطلبات القانونية والتنظيمية المتعلقة بحفظ السجلات والوثائق</p>
          </div>
          
          <div class="benefit-card">
            <div class="benefit-header">
              <div class="benefit-icon">
                <i class="fas fa-medal"></i>
              </div>
              <h3 class="benefit-name">ضمان الجودة</h3>
            </div>
            <p class="benefit-desc">تحقيق التميز التشغيلي وتطبيق أفضل الممارسات في مجال الأرشفة الإلكترونية</p>
          </div>
          
          <div class="benefit-card">
            <div class="benefit-header">
              <div class="benefit-icon">
                <i class="fas fa-lock"></i>
              </div>
              <h3 class="benefit-name">الأمن والموثوقية</h3>
            </div>
            <p class="benefit-desc">حماية البيانات وضمان استمرارية الوصول إلى الوثائق على المدى الطويل</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// No additional script needed for this slide
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
  padding: 2vh 3vw;
}

.slide-content {
  position: relative;
  z-index: 2;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 3vh;
}

.coding-standards, .benefits-section {
  display: flex;
  flex-direction: column;
  gap: 2vh;
}

.section-title {
  font-size: calc(1.3rem + 0.5vw);
  text-align: center;
  color: #ff8c4d;
  margin-bottom: 1vh;
}

.coding-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2vh;
}

.coding-item {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  padding: 1.5vh;
  height: 100%;
  min-height: 180px;
  display: flex;
  flex-direction: column;
  border-right: 3px solid #4da6ff;
  transition: transform 0.3s ease;
}

.coding-item:hover {
  transform: translateY(-3px);
  background: rgba(255, 255, 255, 0.15);
}

.coding-icon {
  width: 40px;
  height: 40px;
  min-width: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(77, 166, 255, 0.2);
  border-radius: 8px;
  font-size: 1.2rem;
  color: #4da6ff;
  margin-bottom: 1vh;
}

.coding-name {
  font-size: 1.1rem;
  color: #4da6ff;
  margin-bottom: 1vh;
  white-space: nowrap;
}

.coding-desc {
  font-size: 0.9rem;
  line-height: 1.5;
  color: #e0e0e0;
  flex-grow: 1;
  display: flex;
  align-items: center;
}

.mt-2 {
  margin-top: 1vh;
}

.benefits-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2vh;
}

.benefit-card {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 12px;
  padding: 1.5vh;
  height: 100%;
  min-height: 120px;
  display: flex;
  flex-direction: column;
  border-right: 3px solid #4da6ff;
  transition: transform 0.3s ease;
}

.benefit-card:hover {
  transform: translateY(-3px);
  background: rgba(255, 255, 255, 0.15);
}

.benefit-header {
  display: flex;
  align-items: center;
  gap: 1vh;
  margin-bottom: 1vh;
}

.benefit-icon {
  width: 35px;
  height: 35px;
  min-width: 35px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(77, 166, 255, 0.2);
  border-radius: 8px;
  font-size: 1.1rem;
  color: #4da6ff;
}

.benefit-name {
  font-size: 1rem;
  margin: 0;
  color: #4da6ff;
  white-space: nowrap;
}

.benefit-desc {
  font-size: 0.9rem;
  line-height: 1.4;
  margin: 0;
  color: #e0e0e0;
  flex-grow: 1;
  display: flex;
  align-items: center;
}

.decorative-circle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(
    circle,
    rgba(77, 166, 255, 0.1) 0%,
    rgba(77, 166, 255, 0) 70%
  );
  z-index: 1;
  pointer-events: none;
  opacity: 0.6;
}

.decorative-circle:nth-child(1) {
  width: 600px;
  height: 600px;
  top: -250px;
  left: -250px;
  background: radial-gradient(
    circle,
    rgba(77, 166, 255, 0.15) 0%,
    rgba(77, 166, 255, 0) 70%
  );
}

.decorative-circle:nth-child(2) {
  width: 500px;
  height: 500px;
  bottom: -200px;
  right: -200px;
  background: radial-gradient(
    circle,
    rgba(255, 140, 77, 0.1) 0%,
    rgba(255, 140, 77, 0) 70%
  );
}

.slide::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.05) 25%, transparent 25%),
    linear-gradient(-45deg, rgba(255, 255, 255, 0.05) 25%, transparent 25%),
    linear-gradient(45deg, transparent 75%, rgba(255, 255, 255, 0.05) 75%),
    linear-gradient(-45deg, transparent 75%, rgba(255, 255, 255, 0.05) 75%);
  background-size: 20px 20px;
  background-position: 0 0, 0 10px, 10px -10px, -10px 0px;
  opacity: 0.15;
  z-index: 1;
  pointer-events: none;
}

@media (max-width: 768px) {
  .coding-grid,
  .benefits-grid {
    grid-template-columns: 1fr;
  }
  
  .coding-item,
  .benefit-card {
    padding: 1.2vh;
  }
  
  .slide {
    padding: 1.5vh 2vw;
  }
  
  .section-title {
    font-size: calc(1.1rem + 0.5vw);
  }
  
  .coding-name,
  .benefit-name {
    font-size: 0.95rem;
  }
  
  .coding-desc,
  .benefit-desc {
    font-size: 0.85rem;
  }
  
  .coding-icon,
  .benefit-icon {
    width: 30px;
    height: 30px;
    font-size: 1rem;
  }
}
</style> 