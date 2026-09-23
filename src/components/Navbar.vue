<script setup>
import { ref } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

window.addEventListener('scroll', handleScroll)
</script>

<template>
  <nav :class="['navbar', { 'scrolled': isScrolled }]">
    <div class="container nav-container">
      <a href="#home" class="logo text-gradient">PSS.</a>
      
      <ul class="nav-links">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#videography">Videography</a></li>
      </ul>
      
      <a href="#contact" class="btn btn-outline nav-btn">Contact Me</a>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 1.5rem 0;
  z-index: 1000;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.navbar.scrolled {
  background: rgba(10, 10, 12, 0.7);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  padding: 1rem 0;
  box-shadow: 0 10px 40px -10px rgba(0, 0, 0, 0.5);
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 2rem;
  font-weight: 800;
  letter-spacing: -1.5px;
}

.nav-links {
  display: flex;
  gap: 3rem;
}

.nav-links a {
  font-weight: 500;
  font-size: 1rem;
  color: var(--text-muted);
  transition: color 0.3s ease;
  position: relative;
  letter-spacing: 0.5px;
}

.nav-links a::after {
  content: '';
  position: absolute;
  width: 5px;
  height: 5px;
  border-radius: 50%;
  bottom: -8px;
  left: 50%;
  transform: translateX(-50%) scale(0);
  background: var(--accent-secondary);
  transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.nav-links a:hover, .nav-links a.active {
  color: #fff;
}

.nav-links a:hover::after {
  transform: translateX(-50%) scale(1);
}

@media (max-width: 768px) {
  .nav-links, .nav-btn {
    display: none;
  }
}
</style>
