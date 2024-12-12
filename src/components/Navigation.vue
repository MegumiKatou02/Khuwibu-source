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
/* .navigation {
  background-color: #FFB7C5;
  padding: 1rem;
  border-radius: 0 0 10px 10px;
  position: fixed;
  width: 1200px;
  top: 0;
  z-index: 1001;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  left: 50%;
  transform: translateX(-50%);
  box-sizing: border-box;
  transition: background-color 0.3s ease;
}

.navigation.scrolled {
    background-color: rgba(255, 183, 197, 0.8);
    backdrop-filter: blur(5px);
}

.nav-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 40px;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

.navigation ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    align-items: center;
    gap: 2rem;
    height: 100%;
}

.navigation a {
    color: white;
    text-decoration: none;
    font-weight: bold;
    padding: 0.5rem 1rem;
    border-radius: 5px;
    transition: background-color 0.3s;
    display: flex;
    align-items: center;
    height: 100%;
}

.navigation a:hover {
    background-color: #FF9AAC;
}

.search-box {
    display: flex;
    align-items: center;
    gap: 5px;
}

.search-box input {
    padding: 8px 12px;
    border: 2px solid #FFB7C5;
    border-radius: 20px;
    outline: none;
    width: 200px;
    transition: all 0.3s ease;
}

.search-box input:focus {
    border-color: #FF9AAC;
    width: 250px;
}

.search-box button {
    background-color: #FFB7C5;
    border: none;
    padding: 8px 15px;
    border-radius: 20px;
    margin-left: 8px;
    cursor: pointer;
    color: white;
    transition: background-color 0.3s ease;
}

.search-box button:hover {
    background-color: #FF9AAC;
} */
</style>