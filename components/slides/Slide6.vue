<template>
  <div class="slide">
    <!-- Decorative Elements -->
    <div class="decorative-circle" style="width: 500px; height: 500px; top: -200px; right: -150px;"></div>
    <div class="decorative-circle" style="width: 400px; height: 400px; bottom: -100px; left: -150px;"></div>
    
    <div class="slide-content">
      <h1 class="slide-title">تكامل الأنظمة والربط البيني</h1>
      
      <!-- Integration Diagram -->
      <div class="system-flow">
        <h3 class="flow-title">تكامل الأنظمة عبر واجهات برمجة التطبيقات (APIs)</h3>
        <pre class="mermaid" ref="mermaidDiv">
          graph LR
          A["أنظمة إدارة الوثائق DMS"] --- C{"واجهات برمجة التطبيقات<br/>APIs"}
          B["أنظمة إدارة المحتوى ECM"] --- C
          C --- D["أنظمة موارد المؤسسة<br/>ERP"]
          C --- E["إدارة علاقات العملاء<br/>CRM"]
          C --- F["أنظمة المؤسسة الأخرى"]
          
          classDef blue fill:#4da6ff20,stroke:#4da6ff,color:#ffffff
          classDef orange fill:#ff8c4d20,stroke:#ff8c4d,color:#ffffff
          classDef white fill:#ffffff10,stroke:#ffffff50,color:#ffffff
          
          class A,B blue
          class C orange
          class D,E,F white
        </pre>
      </div>

      <div class="integration-notes">
        <div class="note-item">
          <i class="fas fa-plug note-icon"></i>
          <div class="note-content">
            <h4>التكامل السلس</h4>
            <p>ربط سلس بين أنظمة المؤسسة المختلفة عبر واجهات برمجة موحدة</p>
          </div>
        </div>
        <div class="note-item">
          <i class="fas fa-sync note-icon"></i>
          <div class="note-content">
            <h4>تبادل البيانات</h4>
            <p>تبادل آمن وفعال للبيانات والوثائق بين الأنظمة المختلفة</p>
          </div>
        </div>
        <div class="note-item">
          <i class="fas fa-shield-alt note-icon"></i>
          <div class="note-content">
            <h4>الأمان والموثوقية</h4>
            <p>ضمان أمن وسلامة البيانات أثناء عمليات التكامل والتبادل</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import mermaid from 'mermaid'

const mermaidDiv = ref(null)

onMounted(() => {
  mermaid.initialize({
    theme: 'dark',
    themeVariables: {
      darkMode: true,
      background: '#1a2a3a',
      primaryColor: '#4da6ff',
      primaryTextColor: '#fff',
      primaryBorderColor: '#4da6ff',
      lineColor: '#4da6ff',
      secondaryColor: '#ff8c4d',
      tertiaryColor: '#2a3f5f'
    },
    fontFamily: 'Arial, Tahoma, sans-serif',
    flowchart: {
      htmlLabels: true,
      curve: 'basis',
      rankSpacing: 50,
      nodeSpacing: 50,
      useMaxWidth: true
    },
    securityLevel: 'loose'
  })

  setTimeout(() => {
    try {
      mermaid.init(undefined, '.mermaid')
    } catch (error) {
      console.error('Mermaid initialization error:', error)
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
  padding: 2vh 3vw;
}

.slide-content {
  position: relative;
  z-index: 2;
  height: 100%;
  display: flex;
  flex-direction: column;
  gap: 2vh;
}

.slide-title {
  font-size: min(2rem, 4vw);
  font-weight: bold;
  margin: 1vh 0;
  text-align: center;
  color: #ffffff;
  position: relative;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
  flex-shrink: 0;
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

.system-flow {
  background: rgba(255, 255, 255, 0.05);
  padding: 1.5vh 2vw;
  border-radius: 15px;
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  flex: 1;
  min-height: 0;
  display: flex;
  flex-direction: column;
}

.flow-title {
  font-size: min(1.2em, 2.5vw);
  font-weight: bold;
  color: #4da6ff;
  margin-bottom: 1vh;
  text-align: center;
  flex-shrink: 0;
}

.mermaid {
  background: rgba(255, 255, 255, 0.03);
  padding: 1vh 1vw;
  border-radius: 10px;
  text-align: center;
  direction: ltr;
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 0;
}

/* Override Mermaid default styles */
:deep(.mermaid svg) {
  width: 100%;
  height: auto !important;
}

.integration-notes {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5vh 2vw;
  width: 100%;
  max-width: 1200px;
  margin: 1vh auto;
  padding: 0 1vw;
  flex-shrink: 0;
}

@media (max-width: 768px) {
  .integration-notes {
    grid-template-columns: 1fr;
    gap: 1vh;
  }
  
  .system-flow {
    flex: 0.8;
  }
}

.note-item {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  padding: 1.2vh 1.2vw;
  display: flex;
  align-items: flex-start;
  gap: 10px;
  transition: all 0.3s ease;
  height: min-content;
}

.note-item:hover {
  background: rgba(77, 166, 255, 0.15);
  transform: translateY(-2px);
}

.note-icon {
  color: #4da6ff;
  font-size: min(20px, 2.5vw);
  margin-top: 2px;
  flex-shrink: 0;
}

.note-content h4 {
  color: #4da6ff;
  font-size: min(16px, 2vw);
  margin: 0 0 2px 0;
}

.note-content p {
  color: #e0e0e0;
  font-size: min(13px, 1.6vw);
  margin: 0;
  line-height: 1.3;
}

.decorative-circle {
  position: absolute;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(77, 166, 255, 0.1) 0%, rgba(77, 166, 255, 0) 70%);
  z-index: 1;
  opacity: 0.3;
}
</style> 