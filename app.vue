<template>
  <div class="app-container">
    <Presentation />
  </div>
</template>

<script setup>
// Component logic here if needed
</script>

<style>
@import url('https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css');
@import url('https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css');
@import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;900&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  height: 100%;
  margin: 0;
  padding: 0;
  font-family: 'Tajawal', sans-serif;
  background-color: #f0f0f0;
}

.app-container {
  height: 100vh;
  display: flex;
  flex-direction: column;
}

#__nuxt {
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.text-white {
  color: white;
}
</style>
