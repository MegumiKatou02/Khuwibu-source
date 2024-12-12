<script setup lang="ts">
import { onMounted, onUnmounted } from 'vue'

function createSakura() {
    const sakuraContainer = document.querySelector('.sakura-container');
    if (!sakuraContainer) return;
    
    const sakura = document.createElement('div');
    const size = Math.random() * 30 + 20;
    const startPositionLeft = Math.random() * window.innerWidth;
    const animationDuration = Math.random() * 6 + 4;

    sakura.classList.add('sakura');
    sakura.style.width = `${size}px`;
    sakura.style.height = `${size}px`;
    sakura.style.left = `${startPositionLeft}px`;
    sakura.style.animationDuration = `${animationDuration}s`;

    sakuraContainer.appendChild(sakura);

    setTimeout(() => {
        sakura.remove();
    }, animationDuration * 1000);
}

let intervalId: number;

onMounted(() => {
    for(let i = 0; i < 10; i++) {
        createSakura();
    }
    intervalId = setInterval(createSakura, 300);
})

onUnmounted(() => {
    if (intervalId) clearInterval(intervalId);
})
</script>

<template>
    <div class="sakura-container"></div>
</template>

<style scoped>
</style> 