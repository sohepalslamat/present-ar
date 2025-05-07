<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle pulse" style="width: 600px; height: 600px; top: -200px; right: -150px;"></div>
    <div class="decorative-circle pulse" style="width: 500px; height: 500px; bottom: -150px; left: -100px;"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">شكرًا لكم</h1>
      
      <div class="conclusion-container">
        <!-- Summary Card -->
        <div class="summary-card">
          <h2 class="card-title">
            <i class="fas fa-check-circle fa-lg"></i>
            ملخص البرنامج التدريبي
          </h2>
          <ul class="benefits-list">
            <li class="benefit-item">
              <i class="fas fa-star benefit-icon"></i>
              <span>أساسيات ومفاهيم الأرشفة الإلكترونية وأهميتها</span>
            </li>
            <li class="benefit-item">
              <i class="fas fa-star benefit-icon"></i>
              <span>تقنيات الحفظ والاسترجاع وأنظمة إدارة الوثائق</span>
            </li>
            <li class="benefit-item">
              <i class="fas fa-star benefit-icon"></i>
              <span>مراحل التحول الرقمي والرقمنة للأرشيف</span>
            </li>
            <li class="benefit-item">
              <i class="fas fa-star benefit-icon"></i>
              <span>التقنيات الناشئة: الذكاء الاصطناعي وسلسلة الكتل</span>
            </li>
            <li class="benefit-item">
              <i class="fas fa-star benefit-icon"></i>
              <span>المعايير الدولية وأفضل الممارسات في الأرشفة</span>
            </li>
          </ul>
        </div>
        
        <!-- Contact Card -->
        <div class="contact-card">
          <h2 class="card-title">
            <i class="fas fa-headset fa-lg"></i>
            للتواصل والاستفسار
          </h2>
          <div class="contact-item">
            <div class="contact-icon">
              <i class="fas fa-envelope"></i>
            </div>
            <div class="contact-info">
              <span class="contact-label">البريد الإلكتروني</span>
              training@example.com
            </div>
          </div>
          <div class="contact-item">
            <div class="contact-icon">
              <i class="fas fa-phone-alt"></i>
            </div>
            <div class="contact-info">
              <span class="contact-label">رقم الهاتف</span>
              +XXX XXXX XXXX
            </div>
          </div>
          <div class="contact-item">
            <div class="contact-icon">
              <i class="fas fa-globe"></i>
            </div>
            <div class="contact-info">
              <span class="contact-label">الموقع الإلكتروني</span>
              www.example.com/e-archiving
            </div>
          </div>
          <div class="contact-item">
            <div class="contact-icon">
              <i class="fas fa-map-marker-alt"></i>
            </div>
            <div class="contact-info">
              <span class="contact-label">العنوان</span>
              مركز التدريب المتخصص - المبنى الرئيسي
            </div>
          </div>
        </div>
      </div>
      
      <!-- Thank You Message -->
      <div class="thank-you-box">
        <h3 class="thank-you-title">نتطلع لمشاركتكم الفعّالة</h3>
        <p class="thank-you-message">نأمل أن يساهم هذا البرنامج في تطوير معارفكم ومهاراتكم في مجال الأرشفة الإلكترونية وتطبيق ما تعلمتموه في بيئة عملكم لتحقيق التميز المؤسسي</p>
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

.slide-title {
  font-size: calc(2rem + 0.5vw);
  font-weight: bold;
  text-align: center;
  color: #ffffff;
  position: relative;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
  margin-bottom: 2vh;
}

.slide-title:after {
  content: "";
  display: block;
  width: 180px;
  height: 4px;
  background: #4da6ff;
  margin: 15px auto 0;
  border-radius: 2px;
}

.conclusion-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 3vw;
  margin-bottom: 3vh;
}

.summary-card, .contact-card {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 20px;
  padding: 2vh 2vw;
  backdrop-filter: blur(5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
  height: 100%;
}

.summary-card {
  border-right: 4px solid #4da6ff;
}

.contact-card {
  border-right: 4px solid #6e48aa;
}

.card-title {
  font-size: calc(1.3rem + 0.2vw);
  font-weight: bold;
  margin-bottom: 2vh;
  display: flex;
  align-items: center;
}

.summary-card .card-title {
  color: #4da6ff;
}

.contact-card .card-title {
  color: #9f7aea;
}

.card-title i {
  margin-left: 15px;
  width: 45px;
  height: 45px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.summary-card .card-title i {
  background: rgba(77, 166, 255, 0.2);
}

.contact-card .card-title i {
  background: rgba(159, 122, 234, 0.2);
}

.benefits-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.benefit-item {
  display: flex;
  align-items: center;
  margin-bottom: 1.5vh;
  font-size: calc(1rem + 0.1vw);
  line-height: 1.5;
  color: #e0e0e0;
}

.benefit-icon {
  color: #4da6ff;
  margin-left: 12px;
  flex-shrink: 0;
}

.contact-item {
  display: flex;
  align-items: center;
  margin-bottom: 2vh;
  font-size: calc(1rem + 0.1vw);
  color: #e0e0e0;
}

.contact-icon {
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 15px;
  color: #9f7aea;
  flex-shrink: 0;
}

.contact-info {
  line-height: 1.3;
}

.contact-label {
  opacity: 0.7;
  font-size: calc(0.8rem + 0.1vw);
  display: block;
}

.thank-you-box {
  background: linear-gradient(135deg, rgba(77, 166, 255, 0.2) 0%, rgba(110, 72, 170, 0.2) 100%);
  border-radius: 20px;
  padding: 3vh 3vw;
  text-align: center;
  backdrop-filter: blur(5px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  width: 80%;
  margin: 0 auto;
}

.thank-you-title {
  font-size: calc(1.5rem + 0.3vw);
  font-weight: bold;
  margin-bottom: 2vh;
  background: linear-gradient(90deg, #4da6ff, #9f7aea);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.thank-you-message {
  font-size: calc(1rem + 0.1vw);
  color: #e0e0e0;
  line-height: 1.6;
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

.pulse {
  animation: pulse 3s infinite;
}

@keyframes pulse {
  0% {
    transform: scale(1);
    opacity: 0.3;
  }
  50% {
    transform: scale(1.05);
    opacity: 0.5;
  }
  100% {
    transform: scale(1);
    opacity: 0.3;
  }
}

@media (max-width: 1024px) {
  .conclusion-container {
    grid-template-columns: 1fr;
    gap: 2vh;
  }
  
  .thank-you-box {
    width: 90%;
  }
  
  .card-title {
    font-size: calc(1.2rem + 0.2vw);
  }
  
  .benefit-item,
  .contact-item,
  .thank-you-message {
    font-size: calc(0.9rem + 0.1vw);
  }
}

@media (max-width: 768px) {
  .slide {
    padding: 1.5vh 2vw;
  }
  
  .slide-title {
    font-size: calc(1.5rem + 0.5vw);
  }
  
  .thank-you-box {
    width: 100%;
    padding: 2vh 2vw;
  }
  
  .thank-you-title {
    font-size: calc(1.3rem + 0.3vw);
  }
  
  .card-title i {
    width: 35px;
    height: 35px;
  }
  
  .contact-icon {
    width: 30px;
    height: 30px;
  }
}
</style> 