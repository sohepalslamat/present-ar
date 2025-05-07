<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle" style="width: 500px; height: 500px; top: -200px; right: -150px;"></div>
    <div class="decorative-circle" style="width: 400px; height: 400px; bottom: -100px; left: -150px;"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">التقنيات الناشئة في الأرشفة الإلكترونية</h1>
      
      <div class="tech-container">
        <!-- AI Card -->
        <div class="tech-card ai-card">
          <div class="tech-header">
            <div class="tech-icon ai-icon">
              <i class="fas fa-brain fa-2x text-white"></i>
            </div>
            <h3 class="tech-title ai-title">الذكاء الاصطناعي والتعلم الآلي</h3>
          </div>
          
          <ul class="feature-list">
            <li class="feature-item ai-feature">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">التصنيف التلقائي للوثائق وفهرستها حسب المحتوى</span>
            </li>
            <li class="feature-item ai-feature">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">استخراج البيانات من النصوص والصور والوثائق الممسوحة ضوئياً</span>
            </li>
            <li class="feature-item ai-feature">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">البحث الدلالي المتقدم وفهم النية من استعلامات البحث</span>
            </li>
            <li class="feature-item ai-feature">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">التعرف على الأنماط واكتشاف العلاقات بين المستندات</span>
            </li>
          </ul>
          
          <div class="tech-apps">
            <div class="app-badge ai-badge">
              <i class="fas fa-search"></i>
              <span>البحث الدلالي</span>
            </div>
            <div class="app-badge ai-badge">
              <i class="fas fa-cubes"></i>
              <span>معالجة اللغة الطبيعية</span>
            </div>
            <div class="app-badge ai-badge">
              <i class="fas fa-eye"></i>
              <span>الرؤية الحاسوبية</span>
            </div>
            <div class="app-badge ai-badge">
              <i class="fas fa-cogs"></i>
              <span>أتمتة العمليات</span>
            </div>
          </div>
          
          <div class="tech-visual">
            <canvas id="ai-chart"></canvas>
          </div>
        </div>
        
        <!-- Blockchain Card -->
        <div class="tech-card blockchain-card">
          <div class="tech-header">
            <div class="tech-icon blockchain-icon">
              <i class="fas fa-link fa-2x text-white"></i>
            </div>
            <h3 class="tech-title blockchain-title">تقنية سلسلة الكتل (Blockchain)</h3>
          </div>
          
          <ul class="feature-list">
            <li class="feature-item blockchain-feature">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">ضمان سلامة الوثائق وعدم تعديلها بعد التسجيل</span>
            </li>
            <li class="feature-item blockchain-feature">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">التحقق من أصالة الوثائق وإثبات المنشأ والملكية</span>
            </li>
            <li class="feature-item blockchain-feature">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">إنشاء سجل تاريخي للأحداث والتغييرات لا يمكن تعديله</span>
            </li>
            <li class="feature-item blockchain-feature">
              <i class="fas fa-check-circle feature-icon"></i>
              <span class="feature-text">استخدام العقود الذكية لأتمتة إدارة دورة حياة الوثائق</span>
            </li>
          </ul>
          
          <div class="tech-apps">
            <div class="app-badge blockchain-badge">
              <i class="fas fa-certificate"></i>
              <span>توثيق المستندات</span>
            </div>
            <div class="app-badge blockchain-badge">
              <i class="fas fa-file-signature"></i>
              <span>العقود الذكية</span>
            </div>
            <div class="app-badge blockchain-badge">
              <i class="fas fa-history"></i>
              <span>سجل التعديلات</span>
            </div>
            <div class="app-badge blockchain-badge">
              <i class="fas fa-fingerprint"></i>
              <span>حماية الهوية</span>
            </div>
          </div>
          
          <div class="tech-visual">
            <canvas id="blockchain-chart"></canvas>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, onBeforeUnmount, ref } from 'vue'
import Chart from 'chart.js/auto'

const aiChartInstance = ref(null)
const blockchainChartInstance = ref(null)

onBeforeUnmount(() => {
  // Cleanup chart instances
  if (aiChartInstance.value) {
    aiChartInstance.value.destroy()
  }
  if (blockchainChartInstance.value) {
    blockchainChartInstance.value.destroy()
  }
})

onMounted(() => {
  // Need to wait a tick for the canvas to be rendered
  setTimeout(() => {
    // AI Chart
    const aiCanvas = document.querySelector('#ai-chart')
    if (aiCanvas instanceof HTMLCanvasElement) {
      const aiCtx = aiCanvas.getContext('2d')
      if (aiCtx) {
        aiChartInstance.value = new Chart(aiCtx, {
          type: 'bar',
          data: {
            labels: ['تصنيف', 'استخراج', 'بحث', 'توصيات', 'أتمتة'],
            datasets: [{
              label: 'مستوى التقدم',
              data: [85, 76, 90, 70, 80],
              backgroundColor: '#4da6ff',
              borderRadius: 5,
              borderWidth: 0
            }]
          },
          options: {
            responsive: true,
            maintainAspectRatio: false,
            scales: {
              y: {
                beginAtZero: true,
                grid: {
                  color: 'rgba(255, 255, 255, 0.1)'
                },
                ticks: {
                  color: '#e0e0e0',
                  font: {
                    size: 12
                  }
                }
              },
              x: {
                grid: {
                  display: false
                },
                ticks: {
                  color: '#e0e0e0',
                  font: {
                    size: 12
                  }
                }
              }
            },
            plugins: {
              legend: {
                display: false
              }
            }
          }
        })
      }
    }

    // Blockchain Chart
    const blockchainCanvas = document.querySelector('#blockchain-chart')
    if (blockchainCanvas instanceof HTMLCanvasElement) {
      const blockchainCtx = blockchainCanvas.getContext('2d')
      if (blockchainCtx) {
        blockchainChartInstance.value = new Chart(blockchainCtx, {
          type: 'doughnut',
          data: {
            labels: ['توثيق المستندات', 'العقود الذكية', 'سجل التعديلات', 'حماية الهوية'],
            datasets: [{
              data: [35, 25, 20, 20],
              backgroundColor: [
                '#6e48aa',
                '#9f7aea',
                '#b794f4',
                '#d6bcfa'
              ],
              borderWidth: 2,
              borderColor: '#0d1b2a'
            }]
          },
          options: {
            responsive: true,
            maintainAspectRatio: false,
            cutout: '60%',
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
  }, 0)
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
  gap: 1vh;
}

.slide-title {
  font-size: min(2.2rem, 4vw);
  font-weight: bold;
  margin: 0.5vh 0;
  text-align: center;
  color: #ffffff;
  position: relative;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

.slide-title:after {
  content: "";
  display: block;
  width: 120px;
  height: 3px;
  background: #4da6ff;
  margin: 0.5vh auto 0;
  border-radius: 2px;
}

.tech-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5vw;
  flex: 1;
  margin-top: 0.5vh;
}

.tech-card {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 15px;
  padding: 1.2vh 1.5vw;
  position: relative;
  overflow: hidden;
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
}

.tech-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.ai-card {
  border-top: 4px solid #4da6ff;
}

.blockchain-card {
  border-top: 4px solid #6e48aa;
}

.tech-header {
  display: flex;
  align-items: center;
  margin-bottom: 1vh;
}

.tech-icon {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 12px;
  flex-shrink: 0;
}

.ai-icon {
  background: linear-gradient(135deg, #3490dc, #4da6ff);
}

.blockchain-icon {
  background: linear-gradient(135deg, #5637a3, #6e48aa);
}

.tech-title {
  font-size: min(1.6em, 3vw);
  font-weight: bold;
}

.ai-title {
  color: #4da6ff;
}

.blockchain-title {
  color: #9f7aea;
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
  position: relative;
  z-index: 1;
}

.feature-icon {
  margin-left: 10px;
  margin-top: 3px;
  flex-shrink: 0;
}

.ai-feature .feature-icon {
  color: #4da6ff;
}

.blockchain-feature .feature-icon {
  color: #9f7aea;
}

.feature-text {
  color: #e0e0e0;
  font-size: min(1em, 2vw);
  line-height: 1.4;
}

.tech-apps {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8vh 1vw;
  margin-top: 1vh;
}

.app-badge {
  background: rgba(255, 255, 255, 0.1);
  padding: 6px 12px;
  border-radius: 16px;
  font-size: min(0.9em, 1.8vw);
  display: flex;
  align-items: center;
}

.app-badge i {
  margin-left: 5px;
}

.ai-badge {
  border: 1px solid rgba(77, 166, 255, 0.3);
}

.blockchain-badge {
  border: 1px solid rgba(159, 122, 234, 0.3);
}

.tech-visual {
  margin-top: 1vh;
  height: 180px;
  position: relative;
  z-index: 1;
  flex-shrink: 0;
}

.decorative-circle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(77, 166, 255, 0.1) 0%, rgba(77, 166, 255, 0) 70%);
  z-index: 1;
  opacity: 0.3;
}

@media (max-width: 768px) {
  .tech-container {
    grid-template-columns: 1fr;
    gap: 1.5vh;
  }
  
  .tech-visual {
    height: 150px;
  }
  
  .tech-apps {
    justify-content: center;
  }

  .tech-title {
    font-size: min(1.4em, 3.5vw);
  }

  .feature-text {
    font-size: min(0.9em, 2.2vw);
  }

  .app-badge {
    font-size: min(0.8em, 2vw);
    padding: 5px 10px;
  }
}
</style> 