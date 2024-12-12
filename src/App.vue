<script setup lang="ts">
import Navigation from './components/Navigation.vue'
import Banner from './components/Banner.vue'
import Home from './components/Home.vue'
import Bot from './components/Bot.vue'
import Info from './components/ServerInfo.vue'
import Contribute from './components/Contribute.vue'
import SakuraEffect from './components/SakuraEffect.vue'

</script>

<template>
  <div class="main-container">
    <SakuraEffect />
    <Navigation />
    <Banner />
    <div id="home">
      <Home />
    </div>
    <div id="bots">
      <Bot />
    </div>
    <div id="info">
      <Info />
    </div>
    <div id="contribute">
      <Contribute />
    </div>
  </div>
</template>

<style scoped>
.main-container {
  padding-top: 72px; /* Chiều cao của navigation + padding */
}

#home, #bots, #info, #contribute {
  min-height: 100vh;
  padding-top: 72px;
  margin-top: -72px;
}
</style>
