<script setup lang="ts">
  function initSlider() {
  const slides = document.querySelectorAll('.slide') as NodeListOf<HTMLElement>;
  const slider = document.querySelector('.slider') as HTMLElement;
  if (!slides.length || !slider) return;

  let currentSlide = 0;
  const slideInterval = 6000;

  function nextSlide() {
    currentSlide++;
    if (currentSlide >= slides.length / 2) {
      slider.style.transition = 'transform 1s ease-in-out';
      slider.style.transform = `translateX(-${currentSlide * 100}%)`;
      
      // Reset khi hết chu kỳ
      setTimeout(() => {
        slider.style.transition = 'none';
        currentSlide = 0;
        slider.style.transform = 'translateX(0)';
      }, 1000); // Chờ hiệu ứng trước khi reset
    } else {
      slider.style.transition = 'transform 1s ease-in-out';
      slider.style.transform = `translateX(-${currentSlide * 100}%)`;
    }
  }

  setInterval(nextSlide, slideInterval);
}


initSlider();
</script>
  
<template>
  <div class="banner">
    <div class="slider">
      <img src="/src/assets/image/MegumiBanner1.jpg" alt="Anime Banner 1" class="slide">
      <img src="/src/assets/image/MegumiBanner2.jpg" alt="Anime Banner 2" class="slide">
      <img src="/src/assets/image/MegumiBanner3.jpg" alt="Anime Banner 3" class="slide">
      <img src="/src/assets/image/MegumiBanner1.jpg" alt="Anime Banner 1" class="slide">
      <img src="/src/assets/image/MegumiBanner2.jpg" alt="Anime Banner 2" class="slide">
      <img src="/src/assets/image/MegumiBanner3.jpg" alt="Anime Banner 3" class="slide">
    </div>
  </div>
</template>

<style scoped>

</style>