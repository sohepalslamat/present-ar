<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div
      class="decorative-circle"
      style="width: 500px; height: 500px; top: -200px; left: -200px"
    ></div>
    <div
      class="decorative-circle"
      style="width: 400px; height: 400px; bottom: -150px; right: -150px"
    ></div>

    <div class="slide-content">
      <h1 class="slide-title">المعايير الدولية للأرشفة الإلكترونية</h1>

      <div class="standards-container">
        <!-- ISO Standards Section -->
        <div class="standard-section">
          <h2 class="section-title">معايير المنظمة الدولية للمعايير (ISO)</h2>

          <div class="standards-grid">
            <!-- ISO 27001 -->
            <div class="standard-card">
              <div class="standard-header">
                <div class="standard-icon">
                  <i class="fas fa-shield-alt"></i>
                </div>
                <h3 class="standard-name">ISO 27001</h3>
              </div>
              <p class="standard-desc">
                معيار أمن المعلومات يحدد متطلبات نظام إدارة أمن المعلومات لحماية
                الأصول المعلوماتية والبيانات
              </p>
            </div>

            <!-- ISO 15801 -->
            <div class="standard-card">
              <div class="standard-header">
                <div class="standard-icon">
                  <i class="fas fa-file-alt"></i>
                </div>
                <h3 class="standard-name">ISO 15801</h3>
              </div>
              <p class="standard-desc">
                معيار إدارة الوثائق الإلكترونية للحفاظ على موثوقية وسلامة
                المعلومات المخزنة إلكترونياً
              </p>
            </div>

            <!-- ISO 14721 -->
            <div class="standard-card">
              <div class="standard-header">
                <div class="standard-icon">
                  <i class="fas fa-archive"></i>
                </div>
                <h3 class="standard-name">ISO 14721 (OAIS)</h3>
              </div>
              <p class="standard-desc">
                نظام معلومات الأرشيف المفتوح - إطار مرجعي لحفظ المعلومات الرقمية
                على المدى الطويل
              </p>
            </div>

            <!-- ISO 16175 -->
            <div class="standard-card">
              <div class="standard-header">
                <div class="standard-icon">
                  <i class="fas fa-project-diagram"></i>
                </div>
                <h3 class="standard-name">ISO 16175</h3>
              </div>
              <p class="standard-desc">
                المبادئ والمتطلبات الوظيفية للسجلات في البيئات الإلكترونية
                المكتبية
              </p>
            </div>
          </div>

          <div class="chart-container">
            <canvas id="compliance-chart" class="compliance-rates"></canvas>
          </div>
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
  const existingChart = Chart.getChart('compliance-chart')
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
  
  const canvas = document.getElementById('compliance-chart')
  if (canvas instanceof HTMLCanvasElement) {
    const ctx = canvas.getContext('2d')
    if (ctx) {
      chartInstance.value = new Chart(ctx, {
        type: "radar",
        data: {
          labels: [
            "الأمن",
            "الموثوقية",
            "قابلية التشغيل البيني",
            "الامتثال القانوني",
            "سهولة الاستخدام",
            "الأداء",
          ],
          datasets: [
            {
              label: "ISO 27001",
              data: [95, 75, 70, 90, 65, 75],
              backgroundColor: "rgba(77, 166, 255, 0.2)",
              borderColor: "rgba(77, 166, 255, 1)",
              pointBackgroundColor: "rgba(77, 166, 255, 1)",
              pointBorderColor: "#fff",
            },
            {
              label: "ISO 15801",
              data: [70, 95, 85, 90, 75, 80],
              backgroundColor: "rgba(255, 140, 77, 0.2)",
              borderColor: "rgba(255, 140, 77, 1)",
              pointBackgroundColor: "rgba(255, 140, 77, 1)",
              pointBorderColor: "#fff",
            },
          ],
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          elements: {
            line: {
              borderWidth: 2,
            },
          },
          scales: {
            r: {
              angleLines: {
                color: "rgba(255, 255, 255, 0.1)",
              },
              grid: {
                color: "rgba(255, 255, 255, 0.1)",
              },
              pointLabels: {
                color: "#e0e0e0",
                font: {
                  size: 12,
                },
              },
              ticks: {
                backdropColor: "transparent",
                color: "rgba(255, 255, 255, 0.5)",
                z: 100,
              },
            },
          },
          plugins: {
            legend: {
              position: "top",
              labels: {
                color: "#e0e0e0",
                font: {
                  size: 12,
                },
                padding: 20,
              },
            },
          },
        },
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
  padding: 2vh 3vw;
}

.slide-content {
  position: relative;
  z-index: 2;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.slide-title {
  font-size: calc(1.5rem + 1vw);
  text-align: center;
  margin-bottom: 2vh;
  color: #4da6ff;
}

.standards-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 2vh;
}

.standard-section {
  display: flex;
  flex-direction: column;
  gap: 2vh;
}

.section-title {
  font-size: calc(1.1rem + 0.5vw);
  color: #ff8c4d;
  margin-bottom: 1vh;
  text-align: center;
}

.standards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1.5vh;
  margin-bottom: 2vh;
}

.standard-card {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  padding: 1.2vh;
  height: 100%;
  min-height: 150px;
  display: flex;
  flex-direction: column;
  transition: transform 0.3s ease;
}

.standard-card:hover {
  transform: translateY(-3px);
  background: rgba(255, 255, 255, 0.15);
}

.standard-header {
  display: flex;
  align-items: center;
  gap: 1vh;
  margin-bottom: 0.8vh;
}

.standard-icon {
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

.standard-name {
  font-size: 1rem;
  margin: 0;
  color: #4da6ff;
  white-space: nowrap;
}

.standard-desc {
  font-size: 0.9rem;
  line-height: 1.4;
  margin: 0;
  color: #e0e0e0;
  flex-grow: 1;
  display: flex;
  align-items: center;
}

.chart-container {
  height: 250px;
  margin: 1vh auto;
  max-width: 800px;
  width: 100%;
  position: relative;
}

.compliance-rates {
  width: 100%;
  height: 100%;
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
}

@media (max-width: 768px) {
  .standards-grid {
    grid-template-columns: 1fr;
  }

  .standard-card {
    padding: 1vh;
  }

  .chart-container {
    height: 200px;
  }

  .slide {
    padding: 1vh 2vw;
  }

  .slide-title {
    font-size: calc(1.2rem + 1vw);
    margin-bottom: 1.5vh;
  }

  .section-title {
    font-size: 1rem;
  }
}
</style> 