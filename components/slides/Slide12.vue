<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle" style="width: 500px; height: 500px; top: -200px; right: -150px;"></div>
    <div class="decorative-circle" style="width: 400px; height: 400px; bottom: -150px; left: -150px;"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">مقارنة أنظمة الأرشيف الإلكتروني</h1>
      
      <div class="charts-container">
        <!-- Radar Chart -->
        <div class="chart-box">
          <h3 class="chart-title">مقارنة الخصائص الرئيسية</h3>
          <div class="radar-chart-container">
            <canvas id="systems-radar-chart"></canvas>
          </div>
        </div>
        
        <!-- Features Table -->
        <div class="chart-box">
          <h3 class="chart-title">مقارنة الميزات الأساسية</h3>
          <table class="features-table">
            <thead>
              <tr>
                <th>الميزة</th>
                <th>Alfresco</th>
                <th>OpenText</th>
                <th>M-Files</th>
                <th>SharePoint</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>دعم الذكاء الاصطناعي</td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-adjust partial-icon"></i></td>
              </tr>
              <tr>
                <td>سهولة التخصيص</td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-adjust partial-icon"></i></td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
              </tr>
              <tr>
                <td>التكامل مع الأنظمة الأخرى</td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-adjust partial-icon"></i></td>
              </tr>
              <tr>
                <td>إدارة السجلات والامتثال</td>
                <td><i class="fas fa-adjust partial-icon"></i></td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-adjust partial-icon"></i></td>
              </tr>
              <tr>
                <td>التكلفة والقيمة</td>
                <td><i class="fas fa-check-circle check-icon"></i></td>
                <td><i class="fas fa-times-circle missing-icon"></i></td>
                <td><i class="fas fa-adjust partial-icon"></i></td>
                <td><i class="fas fa-adjust partial-icon"></i></td>
              </tr>
            </tbody>
          </table>
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

.charts-container {
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: 25px;
  flex-grow: 1;
  margin: auto;
  width: 100%;
  max-height: 75vh;
}

.chart-box {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 15px;
  padding: 20px;
  height: 100%;
}

.chart-title {
  font-size: calc(1.1rem + 0.2vw);
  font-weight: bold;
  color: #4da6ff;
  margin-bottom: 15px;
  text-align: center;
}

.radar-chart-container {
  height: calc(100% - 50px);
  width: 100%;
}

.features-table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  color: #e0e0e0;
  font-size: calc(0.85rem + 0.1vw);
}

.features-table th {
  background: rgba(77, 166, 255, 0.1);
  padding: 10px;
  text-align: center;
  font-weight: bold;
  color: #4da6ff;
}

.features-table td {
  padding: 8px;
  text-align: center;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.features-table tr:last-child td {
  border-bottom: none;
}

.features-table tr:nth-child(even) {
  background: rgba(255, 255, 255, 0.03);
}

.check-icon { color: #48bb78; }
.partial-icon { color: #ed8936; }
.missing-icon { color: #e53e3e; }

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
  .charts-container {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  
  .slide {
    padding: 1.5vh 2vw;
  }
  
  .slide-title {
    font-size: calc(1.4rem + 0.5vw);
  }
  
  .chart-title {
    font-size: calc(1rem + 0.2vw);
  }
  
  .features-table {
    font-size: calc(0.8rem + 0.1vw);
  }
}
</style> 