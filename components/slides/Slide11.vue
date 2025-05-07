<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle" style="width: 500px; height: 500px; top: -200px; right: -150px;"></div>
    <div class="decorative-circle" style="width: 400px; height: 400px; bottom: -150px; left: -150px;"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">مقارنة أنظمة الأرشيف الإلكتروني</h1>
      
      <div class="systems-comparison">
        <!-- Alfresco -->
        <div class="system-card alfresco">
          <div class="system-logo">
            <div class="system-icon alfresco-icon">
              <i class="fas fa-sitemap fa-lg text-white"></i>
            </div>
          </div>
          <h3 class="system-name" style="color: #4da6ff;">Alfresco</h3>
          <p class="system-desc">نظام مفتوح المصدر لإدارة المحتوى والوثائق مع مرونة عالية في التخصيص</p>
          <ul class="feature-list">
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #4da6ff;"></i>
              <span>مفتوح المصدر مع خيارات مدفوعة</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #4da6ff;"></i>
              <span>تكامل سير العمل وإدارة العمليات</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #4da6ff;"></i>
              <span>واجهة برمجة تطبيقات REST مفتوحة</span>
            </li>
          </ul>
        </div>
        
        <!-- OpenText -->
        <div class="system-card opentext">
          <div class="system-logo">
            <div class="system-icon opentext-icon">
              <i class="fas fa-globe fa-lg text-white"></i>
            </div>
          </div>
          <h3 class="system-name" style="color: #48bb78;">OpenText</h3>
          <p class="system-desc">حل متكامل للمؤسسات الكبيرة يوفر إدارة شاملة للمحتوى والسجلات</p>
          <ul class="feature-list">
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #48bb78;"></i>
              <span>حل متكامل للمؤسسات الكبيرة</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #48bb78;"></i>
              <span>إدارة دورة الحياة الكاملة للسجلات</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #48bb78;"></i>
              <span>حلول متخصصة لقطاعات مختلفة</span>
            </li>
          </ul>
        </div>
        
        <!-- M-Files -->
        <div class="system-card mfiles">
          <div class="system-logo">
            <div class="system-icon mfiles-icon">
              <i class="fas fa-folder-open fa-lg text-white"></i>
            </div>
          </div>
          <h3 class="system-name" style="color: #ed8936;">M-Files</h3>
          <p class="system-desc">نظام إدارة وثائق متقدم يركز على التصنيف الوصفي بدلا من هيكل المجلدات</p>
          <ul class="feature-list">
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #ed8936;"></i>
              <span>نهج قائم على البيانات الوصفية</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #ed8936;"></i>
              <span>بحث متقدم وتصفية سريعة</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #ed8936;"></i>
              <span>تكامل مع تطبيقات مايكروسوفت أوفيس</span>
            </li>
          </ul>
        </div>
        
        <!-- SharePoint -->
        <div class="system-card sharepoint">
          <div class="system-logo">
            <div class="system-icon sharepoint-icon">
              <i class="fas fa-share-alt fa-lg text-white"></i>
            </div>
          </div>
          <h3 class="system-name" style="color: #9f7aea;">SharePoint</h3>
          <p class="system-desc">منصة تعاونية من مايكروسوفت تتكامل بسهولة مع منتجات أوفيس 365</p>
          <ul class="feature-list">
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #9f7aea;"></i>
              <span>تكامل قوي مع حزمة مايكروسوفت</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #9f7aea;"></i>
              <span>قدرات تعاون وتشارك متقدمة</span>
            </li>
            <li class="feature-item">
              <i class="fas fa-check-circle feature-icon" style="color: #9f7aea;"></i>
              <span>سهولة إنشاء سير العمل وتطويره</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, onBeforeUnmount, nextTick, ref } from 'vue'
import Chart from 'chart.js/auto'

const chartInstance = ref(null)

// Helper function to destroy any existing chart
const destroyChart = () => {
  // Destroy our instance if it exists
  if (chartInstance.value) {
    chartInstance.value.destroy()
    chartInstance.value = null
  }
  
  // Also check for any other instances of this chart
  const existingChart = Chart.getChart('systems-radar-chart')
  if (existingChart) {
    existingChart.destroy()
  }
}

onBeforeUnmount(() => {
  destroyChart()
})

onMounted(async () => {
  // Ensure DOM is ready
  await nextTick()
  
  // Clean up any existing chart first
  destroyChart()
  
  const canvas = document.getElementById('systems-radar-chart')
  if (canvas instanceof HTMLCanvasElement) {
    const ctx = canvas.getContext('2d')
    if (ctx) {
      chartInstance.value = new Chart(ctx, {
        type: 'radar',
        data: {
          labels: [
            'سهولة الاستخدام',
            'المرونة والتكيف',
            'قوة البحث',
            'التكامل مع الأنظمة',
            'الأمن والامتثال',
            'قابلية التوسع',
            'القيمة مقابل التكلفة'
          ],
          datasets: [
            {
              label: 'Alfresco',
              data: [75, 90, 85, 95, 80, 88, 90],
              backgroundColor: 'rgba(77, 166, 255, 0.2)',
              borderColor: 'rgba(77, 166, 255, 1)',
              pointBackgroundColor: 'rgba(77, 166, 255, 1)'
            },
            {
              label: 'OpenText',
              data: [70, 75, 90, 90, 95, 85, 65],
              backgroundColor: 'rgba(72, 187, 120, 0.2)',
              borderColor: 'rgba(72, 187, 120, 1)',
              pointBackgroundColor: 'rgba(72, 187, 120, 1)'
            },
            {
              label: 'M-Files',
              data: [85, 80, 95, 85, 85, 80, 75],
              backgroundColor: 'rgba(237, 137, 54, 0.2)',
              borderColor: 'rgba(237, 137, 54, 1)',
              pointBackgroundColor: 'rgba(237, 137, 54, 1)'
            },
            {
              label: 'SharePoint',
              data: [90, 75, 70, 80, 75, 90, 80],
              backgroundColor: 'rgba(159, 122, 234, 0.2)',
              borderColor: 'rgba(159, 122, 234, 1)',
              pointBackgroundColor: 'rgba(159, 122, 234, 1)'
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          elements: {
            line: {
              borderWidth: 2
            }
          },
          scales: {
            r: {
              angleLines: {
                color: 'rgba(255, 255, 255, 0.1)'
              },
              grid: {
                color: 'rgba(255, 255, 255, 0.1)'
              },
              pointLabels: {
                color: '#e0e0e0',
                font: {
                  size: 12
                }
              },
              ticks: {
                backdropColor: 'transparent',
                color: 'rgba(255, 255, 255, 0.5)',
                showLabelBackdrop: false,
                z: 100
              }
            }
          },
          plugins: {
            legend: {
              position: 'top',
              labels: {
                color: '#e0e0e0',
                font: {
                  size: 12
                },
                padding: 15
              }
            }
          }
        }
      })
    }
  }
})
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
  padding: 1vh 3vw;
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
  font-size: calc(1.8rem + 0.5vw);
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
  width: 150px;
  height: 4px;
  background: #4da6ff;
  margin: 15px auto 0;
  border-radius: 2px;
}

.systems-comparison {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2vh;
  margin-bottom: 2vh;
  height: 85vh;
}

.system-card {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  padding: 1.5vh;
  text-align: center;
  transition: all 0.3s ease;
  border-top: 4px solid;
  height: 100%;
}

.system-card:hover {
  transform: translateY(-5px);
  background: rgba(255, 255, 255, 0.15);
}

.alfresco { border-color: #4da6ff; }
.opentext { border-color: #48bb78; }
.mfiles { border-color: #ed8936; }
.sharepoint { border-color: #9f7aea; }

.system-logo {
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 15px;
}

.system-icon {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
}

.alfresco-icon { background: linear-gradient(135deg, #3182ce, #4da6ff); }
.opentext-icon { background: linear-gradient(135deg, #38a169, #48bb78); }
.mfiles-icon { background: linear-gradient(135deg, #dd6b20, #ed8936); }
.sharepoint-icon { background: linear-gradient(135deg, #805ad5, #9f7aea); }

.system-name {
  font-size: calc(1.1rem + 0.2vw);
  font-weight: bold;
  margin-bottom: 10px;
}

.system-desc {
  font-size: calc(0.9rem + 0.1vw);
  color: #e0e0e0;
  margin-bottom: 15px;
  min-height: 60px;
}

.feature-list {
  list-style: none;
  padding: 0;
  text-align: right;
}

.feature-item {
  display: flex;
  align-items: center;
  font-size: calc(0.85rem + 0.1vw);
  margin-bottom: 8px;
  color: #e0e0e0;
}

.feature-icon {
  margin-left: 8px;
  flex-shrink: 0;
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

@media (max-width: 768px) {
  .systems-comparison {
    grid-template-columns: 1fr;
  }
  
  .system-card {
    padding: 1.2vh;
  }
  
  .slide {
    padding: 1.5vh 2vw;
  }
  
  .slide-title {
    font-size: calc(1.4rem + 0.5vw);
  }
  
  .system-name {
    font-size: calc(1rem + 0.2vw);
  }
  
  .system-desc,
  .feature-item {
    font-size: calc(0.8rem + 0.1vw);
  }
  
  .system-icon,
  .feature-icon {
    width: 30px;
    height: 30px;
    font-size: 1rem;
  }
}
</style> 