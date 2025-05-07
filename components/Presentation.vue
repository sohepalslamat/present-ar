<template>
  <div class="presentation-container">
    <!-- Decorative Elements -->
    <div class="decorative-circle circle-1"></div>
    <div class="decorative-circle circle-2"></div>
    
    <div class="slides-container">
      <div v-if="currentSlide === 1" class="slide">
        <SlidesSlide1  />
      </div>
      <div v-if="currentSlide === 2" class="slide">
        <SlidesSlide2  />
      </div>
      <div v-if="currentSlide === 3" class="slide">
        <SlidesSlide3  />
      </div>
      <div v-if="currentSlide === 4" class="slide">
        <SlidesSlide4  />
      </div>
      <div v-if="currentSlide === 5" class="slide">
        <SlidesSlide5  />
      </div>
      <div v-if="currentSlide === 6" class="slide">
        <SlidesSlide6  />
      </div>
      <div v-if="currentSlide === 7" class="slide">
        <SlidesSlide7  />
      </div>
      <div v-if="currentSlide === 8" class="slide">
        <SlidesSlide8  />
      </div>
      <div v-if="currentSlide === 9" class="slide">
        <SlidesSlide9  />
      </div>
      <div v-if="currentSlide === 10" class="slide">
        <SlidesSlide10  />
      </div>
      <div v-if="currentSlide === 11" class="slide">
        <SlidesSlide11  />
      </div>
      <div v-if="currentSlide === 12" class="slide">
        <SlidesSlide12  />
      </div>
      <div v-if="currentSlide === 13" class="slide">
        <SlidesSlide13  />
      </div>
      <!-- Other slides will be added here -->
    </div>

    <div class="controls">
      <button @click="prevSlide">السابق</button>
      <span class="slide-number">شريحة {{ currentSlide }} من {{ totalSlides }}</span>
      <button @click="nextSlide">التالي</button>
      <button @click="toggleFullscreen" class="fullscreen-btn">
        <span v-if="!isFullscreen">ملء الشاشة</span>
        <span v-else>إنهاء ملء الشاشة</span>
      </button>
    </div>
    <div class="preview-mode" @click="togglePreview">عرض المصغرات</div>

    <div class="preview-container" :class="{ active: showPreview }" @click="closePreview">
      <div class="preview-grid">
        <div v-for="slide in totalSlides" 
             :key="slide" 
             class="preview-item"
             :class="{ active: currentSlide === slide }"
             @click="selectSlide(slide)">          
          <p>شريحة {{ slide }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

const route = useRoute()
const router = useRouter()
const currentSlide = ref(Number(route.query.slide) || 1)
const totalSlides = 13
const showPreview = ref(false)
const isFullscreen = ref(false)

function showSlide(slideNumber) {
  currentSlide.value = slideNumber
  // Update URL when slide changes
  router.push({
    query: {
      ...route.query,
      slide: slideNumber.toString()
    }
  })
}

function nextSlide() {
  if (currentSlide.value < totalSlides) {
    showSlide(currentSlide.value + 1)
  }
}

function prevSlide() {
  if (currentSlide.value > 1) {
    showSlide(currentSlide.value - 1)
  }
}

function togglePreview() {
  showPreview.value = !showPreview.value
}

function closePreview(e) {
  if (e.target.classList.contains('preview-container')) {
    showPreview.value = false
  }
}

function selectSlide(slideNumber) {
  showSlide(slideNumber)
  showPreview.value = false
}

function toggleFullscreen() {
  if (!document.fullscreenElement) {
    document.documentElement.requestFullscreen()
    isFullscreen.value = true
  } else {
    if (document.exitFullscreen) {
      document.exitFullscreen()
      isFullscreen.value = false
    }
  }
}

// Enhanced Keyboard navigation
onMounted(() => {
  window.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowRight' || e.key === 'Backspace') {
      prevSlide()
    } else if (e.key === 'ArrowLeft' || e.code === 'Space') {
      nextSlide()
      // Prevent page scroll when space is pressed
      if (e.code === 'Space') {
        e.preventDefault()
      }
    }
  })

  // Listen for fullscreen changes
  document.addEventListener('fullscreenchange', () => {
    isFullscreen.value = !!document.fullscreenElement
  })
})

onUnmounted(() => {
  // Clean up event listeners
  document.removeEventListener('fullscreenchange', () => {
    isFullscreen.value = !!document.fullscreenElement
  })
})
</script>

<style scoped>
.presentation-container {
  flex: 1;
  position: relative;
  overflow: hidden;
  height: 100vh;
  direction: rtl;
  background: linear-gradient(135deg, #1a2a3a 0%, #0d1b2a 100%);
}

.presentation-container::before {
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

.decorative-circle {
  position: absolute;
  border-radius: 50%;
  z-index: 1;
  pointer-events: none;
  opacity: 0.6;
}

.circle-1 {
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

.circle-2 {
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

.slides-container {
  width: 100%;
  height: 100%;
  position: relative;
  z-index: 2;
}

.slide {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 1;
  display: block;
  transition: opacity 0.5s ease-in-out;
  pointer-events: auto;
  background: transparent;
}

.slide.active {
  opacity: 1;
  display: block;
  pointer-events: auto;
}

.controls {
  position: fixed;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  background: rgba(0, 0, 0, 0.7);
  padding: 10px 20px;
  border-radius: 30px;
  display: flex;
  gap: 15px;
  z-index: 1000;
  opacity: 0.1;
  transition: opacity 0.3s ease;
}

.controls:hover {
  opacity: 1;
}

.controls button {
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  font-size: 16px;
  padding: 5px 10px;
  border-radius: 5px;
  transition: background-color 0.3s;
}

.controls button:hover {
  background-color: rgba(255, 255, 255, 0.2);
}

.slide-number {
  color: white;
  font-size: 14px;
  padding: 5px 10px;
}

.preview-mode {
  position: fixed;
  top: 20px;
  right: 20px;
  background: rgba(0, 0, 0, 0.7);
  padding: 10px;
  border-radius: 5px;
  color: white;
  cursor: pointer;
  z-index: 1000;
  opacity: 0.1;
  transition: opacity 0.3s ease;
}

.preview-mode:hover {
  opacity: 1;
}

.preview-container {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.9);
  z-index: 2000;
  padding: 20px;
  overflow-y: auto;
}

.preview-container.active {
  display: block;
}

.preview-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
  padding: 20px;
}

.preview-item {
  background: #1a2a3a;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
  transition: transform 0.3s;
  height: 150px;
  overflow: hidden;
  position: relative;
  border: 1px solid rgba(77, 166, 255, 0.2);
}

.preview-item.active {

  border-color: rgba(77, 139, 255, 0.4);
  box-shadow: 0 0 15px rgba(77, 139, 255, 0.2);
  border-width: 2px;
}

.preview-item:hover {
  transform: scale(1.05);
  border-color: rgba(77, 166, 255, 0.4);
  box-shadow: 0 0 15px rgba(77, 166, 255, 0.2);
}

.preview-item p {
  text-align: center;
  margin-top: 5px;
  color: #ffffff;
  position: absolute;
  bottom: 5px;
  left: 0;
  right: 0;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.5);
}

.fullscreen-btn {
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  font-size: 16px;
  padding: 5px 10px;
  border-radius: 5px;
  transition: background-color 0.3s;
  margin-left: 15px;
}

.fullscreen-btn:hover {
  background-color: rgba(255, 255, 255, 0.2);
}
</style> 