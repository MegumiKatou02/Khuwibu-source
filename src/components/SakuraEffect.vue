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
/* .sakura-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    pointer-events: none;
    z-index: 999;
}

.sakura {
    position: absolute;
    top: -50px;
    background-color: #FFB7C5;
    border-radius: 50%;
    animation: fall linear forwards;
    opacity: 0.7;
    box-shadow: 0 0 10px rgba(255, 183, 197, 0.5);
}

@keyframes fall {
    0% {
        transform: translateY(0) rotate(0deg);
    }
    25% {
        transform: translateY(25vh) rotate(180deg) translateX(100px);
    }
    50% {
        transform: translateY(50vh) rotate(360deg) translateX(-100px);
    }
    75% {
        transform: translateY(75vh) rotate(540deg) translateX(100px);
    }
    100% {
        transform: translateY(105vh) rotate(720deg);
    }
} */
</style> 