<template>
  <div class="slide-2">
    <div class="slide-content">
      <h1 class="slide-title">الأهداف التفصيلية للبرنامج</h1>
      
      <div class="goals-container">
        <!-- Goal 1 -->
        <div class="goal-item">
          <div class="goal-icon">
            <i class="fas fa-lightbulb fa-lg"></i>
          </div>
          <div class="goal-content">
            <h3 class="goal-title">فهم أهمية الأرشيف الإلكتروني</h3>
            <p class="goal-details">التعريف بأهمية الأرشيف • القيمة الاستراتيجية والقانونية للوثائق • تحليل التحديات المعاصرة</p>
          </div>
        </div>
        
        <!-- Goal 2 -->
        <div class="goal-item">
          <div class="goal-icon">
            <i class="fas fa-file-alt fa-lg"></i>
          </div>
          <div class="goal-content">
            <h3 class="goal-title">التمييز بين أنواع الوثائق</h3>
            <p class="goal-details">خصائص الوثيقة الإلكترونية • التوقيع الرقمي • مقارنة الحفظ السحابي والمحلي</p>
          </div>
        </div>
        
        <!-- Goal 3 -->
        <div class="goal-item">
          <div class="goal-icon">
            <i class="fas fa-cogs fa-lg"></i>
          </div>
          <div class="goal-content">
            <h3 class="goal-title">تطبيق تقنيات الحفظ والاسترجاع</h3>
            <p class="goal-details">أنظمة إدارة المحتوى • البحث الدلالي • الربط مع الأنظمة المؤسسية</p>
          </div>
        </div>
        
        <!-- Goal 4 -->
        <div class="goal-item">
          <div class="goal-icon">
            <i class="fas fa-digital-tachograph fa-lg"></i>
          </div>
          <div class="goal-content">
            <h3 class="goal-title">إدارة التحول الرقمي للأرشيف</h3>
            <p class="goal-details">تخطيط رقمنة الوثائق • استخدام الماسحات الضوئية الذكية • تصميم خطط التدريب</p>
          </div>
        </div>
        
        <!-- Goal 5 -->
        <div class="goal-item">
          <div class="goal-icon">
            <i class="fas fa-tags fa-lg"></i>
          </div>
          <div class="goal-content">
            <h3 class="goal-title">التصنيف والفهرسة الرقمية</h3>
            <p class="goal-details">تصميم هياكل تصنيف الميتاداتا • تطبيق الذكاء الاصطناعي في الفهرسة • توحيد الترميز</p>
          </div>
        </div>
        
        <!-- Goal 6 -->
        <div class="goal-item">
          <div class="goal-icon">
            <i class="fas fa-shield-alt fa-lg"></i>
          </div>
          <div class="goal-content">
            <h3 class="goal-title">ضمان الأمن والامتثال</h3>
            <p class="goal-details">تطبيق معايير أمن المعلومات • استخدام تقنيات سلسلة الكتل • حماية البيانات</p>
          </div>
        </div>
        
        <!-- Goal 7 -->
        <div class="goal-item">
          <div class="goal-icon">
            <i class="fas fa-chart-line fa-lg"></i>
          </div>
          <div class="goal-content">
            <h3 class="goal-title">تقييم الأنظمة الحديثة</h3>
            <p class="goal-details">مقارنة أنظمة الأرشيف الإلكتروني • حلول الأرشيف المدعومة بالذكاء الاصطناعي</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.slide-2 {
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #1a2a3a 0%, #0d1b2a 100%);
  color: #ffffff;
  overflow: hidden;
  position: relative;
}

.slide-content {
  padding: 40px 60px;
  height: 100%;
  position: relative;
  z-index: 1;
}

.slide-title {
  font-size: 48px;
  font-weight: bold;
  margin-bottom: 30px;
  text-align: center;
  color: #ffffff;
  position: relative;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

.slide-title:after {
  content: "";
  display: block;
  width: 150px;
  height: 4px;
  background: #4da6ff;
  margin: 15px auto 0;
  border-radius: 2px;
}

.goals-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 25px;
  margin-top: 20px;
}

.goal-item {
  display: flex;
  background-color: rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  padding: 15px;
  border-right: 4px solid #4da6ff;
  transition: all 0.3s ease;
}

.goal-item:hover {
  background-color: rgba(77, 166, 255, 0.15);
  transform: translateY(-3px);
}

.goal-icon {
  background-color: rgba(77, 166, 255, 0.2);
  min-width: 50px;
  height: 50px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 15px;
  color: #4da6ff;
}

.goal-content {
  flex: 1;
}

.goal-title {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 8px;
  color: #4da6ff;
}

.goal-details {
  font-size: 14px;
  color: #e0e0e0;
  line-height: 1.4;
}

/* Decorative circles */
.slide-2::before,
.slide-2::after {
  content: "";
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(77, 166, 255, 0.1) 0%, rgba(77, 166, 255, 0) 70%);
}

.slide-2::before {
  width: 500px;
  height: 500px;
  top: -250px;
  right: -100px;
}

.slide-2::after {
  width: 400px;
  height: 400px;
  bottom: -150px;
  left: -150px;
}
</style> 