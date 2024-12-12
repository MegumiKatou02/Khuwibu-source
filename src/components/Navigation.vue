<script setup lang="ts">
const scrollToSection = (e: Event, id: string) => {
  e.preventDefault();
  const element = document.getElementById(id);
  if (element) {
    const offset = 72;
    const elementPosition = element.getBoundingClientRect().top;
    const offsetPosition = elementPosition + window.scrollY - offset;
    
    window.scrollTo({
      top: offsetPosition,
      behavior: 'smooth'
    });
  }
}
</script>

<template>
  <nav class="navigation" role="navigation">
    <div class="nav-container">
      <button class="mobile-menu-btn" aria-label="Menu">
        <i class="fas fa-bars"></i>
      </button>
      <div class="search-box" role="search">
        <input type="text" placeholder="Tìm kiếm..." aria-label="Search" id="searchInput">
        <button type="submit" aria-label="Tìm kiếm">
          <i class="fas fa-search"></i>
          <span>Tìm kiếm</span>
        </button>
      </div>
      <ul role="menubar">
        <li role="none"><a @click="(e) => scrollToSection(e, 'home')" href="#" class="active" role="menuitem">Trang chủ</a></li>
        <li role="none"><a @click="(e) => scrollToSection(e, 'bots')" href="#" role="menuitem">Bot Server</a></li>
        <li role="none"><a @click="(e) => scrollToSection(e, 'info')" href="#" role="menuitem">Thông tin</a></li>
        <li role="none"><a @click="(e) => scrollToSection(e, 'contribute')" href="#" role="menuitem">Đóng góp</a></li>
        <li role="none"><a href="/Khu-Wibu-Page/document.html" role="menuitem">Tài liệu</a></li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>

</style>