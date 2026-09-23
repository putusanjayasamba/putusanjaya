<script setup>
// Hero Section
import { ref } from 'vue'
import profileImg from '../../putu.webp'
</script>

<template>
  <section class="hero">
    <div class="hero-bg-gradient"></div>
    <div class="container hero-container">
      <div class="hero-content">
        <h2 class="greeting animate-fade-in-up">Hello, I am</h2>
        <h1 class="name animate-fade-in-up delay-1">
          <span class="text-gradient">Putu Sanjaya Samba</span>
        </h1>
        <h3 class="role animate-fade-in-up delay-2">
          Informatics Student & <br/> <span class="highlight">Visual Creator</span>
        </h3>
        <p class="description animate-fade-in-up delay-2">
          Based in Bali. I blend the logical precision of programming with the aesthetic eye of a photographer to build stunning, high-performance digital experiences.
        </p>
        
        <div class="cta-group animate-fade-in-up delay-3">
          <a href="#projects" class="btn btn-primary">View Web Projects</a>
          <a href="#videography" class="btn btn-outline">Explore Videography</a>
        </div>
      </div>
      
      <div class="hero-image-wrapper animate-fade-in-up delay-2">
        <div class="glow-effect"></div>
        <div class="image-frame">
          <img :src="profileImg" alt="Putu Sanjaya Samba" class="hero-image" onerror="this.src='https://via.placeholder.com/500'"/>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
}

.hero-bg-gradient {
  position: absolute;
  top: -10%;
  left: -10%;
  width: 50vw;
  height: 50vw;
  background: radial-gradient(circle, rgba(138,43,226,0.15) 0%, rgba(10,10,12,0) 70%);
  z-index: -1;
  filter: blur(100px);
}

.hero-container {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 5rem;
  align-items: center;
  padding-top: 100px;
}

.greeting {
  font-size: 1.4rem;
  font-weight: 400;
  color: var(--text-muted);
  margin-bottom: 0.8rem;
  letter-spacing: 2px;
  text-transform: uppercase;
}

.name {
  font-size: 5.5rem;
  font-weight: 800;
  line-height: 1.05;
  margin-bottom: 1.5rem;
  letter-spacing: -2px;
}

.role {
  font-size: 2.2rem;
  font-weight: 600;
  line-height: 1.3;
  margin-bottom: 1.8rem;
  color: var(--text-main);
}

.highlight {
  color: var(--accent-secondary);
  font-style: italic;
  font-weight: 700;
}

.description {
  font-size: 1.15rem;
  color: var(--text-muted);
  max-width: 550px;
  margin-bottom: 3rem;
  line-height: 1.8;
}

.cta-group {
  display: flex;
  gap: 1.5rem;
}

.hero-image-wrapper {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.glow-effect {
  position: absolute;
  width: 350px;
  height: 350px;
  background: conic-gradient(from 180deg at 50% 50%, var(--accent-primary) 0deg, var(--accent-secondary) 180deg, var(--accent-primary) 360deg);
  border-radius: 50%;
  filter: blur(90px);
  opacity: 0.6;
  z-index: -1;
  animation: spin 8s linear infinite;
}

.image-frame {
  position: relative;
  padding: 10px;
  background: rgba(255, 255, 255, 0.03);
  border-radius: 40px;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 30px 60px rgba(0,0,0,0.5);
  backdrop-filter: blur(10px);
}

.hero-image {
  width: 100%;
  max-width: 450px;
  border-radius: 30px;
  object-fit: cover;
  aspect-ratio: 4/5;
  filter: contrast(1.1) brightness(0.9);
  transition: all 0.5s ease;
}

.image-frame:hover .hero-image {
  filter: contrast(1.1) brightness(1.1);
  transform: scale(1.02);
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

@media (max-width: 1200px) {
  .name { font-size: 4.5rem; }
}

@media (max-width: 992px) {
  .hero-container {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 4rem;
  }
  
  .name { font-size: 4rem; }
  .description { margin: 0 auto 3rem; }
  .cta-group { justify-content: center; }
  
  .hero-image-wrapper {
    order: -1;
  }
}
</style>
