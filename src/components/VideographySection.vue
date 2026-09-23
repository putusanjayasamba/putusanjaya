<script setup>
const videos = [
  {
    id: 1,
    title: 'Wedding Documentation Bali',
    client: 'Balinese Traditional Wedding',
    description: 'A cinematic wedding documentation capturing the sacred, romantic, and meaningful nuances of a traditional Balinese wedding. Every frame is carefully directed to immortalize precious moments.',
    image: 'https://images.unsplash.com/photo-1583939000240-6901166c483a?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80',
    link: '#'
  }
]
</script>

<template>
  <section class="section">
    <div class="container">
      <h2 class="section-title">Videography Works</h2>
      
      <div class="video-showcase">
        <div v-for="video in videos" :key="video.id" class="video-card glass-card">
          <div class="video-thumbnail">
            <div class="video-overlay"></div>
            <img :src="video.image" :alt="video.title" />
            <a :href="video.link" class="play-btn">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M8 5V19L19 12L8 5Z" fill="currentColor"/>
              </svg>
            </a>
          </div>
          <div class="video-details">
            <span class="client-name">{{ video.client }}</span>
            <h3 class="video-title">{{ video.title }}</h3>
            <p class="video-desc">{{ video.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.video-showcase {
  max-width: 1000px;
  margin: 0 auto;
}

.video-card {
  padding: 0;
  overflow: hidden;
  border-radius: 24px;
  border: 1px solid rgba(255, 255, 255, 0.05);
}

.video-thumbnail {
  position: relative;
  width: 100%;
  height: 500px;
  overflow: hidden;
}

.video-overlay {
  position: absolute;
  top: 0; left: 0; right: 0; bottom: 0;
  background: linear-gradient(to top, rgba(10, 10, 12, 0.8), transparent 50%);
  z-index: 1;
}

.video-thumbnail img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.8s cubic-bezier(0.2, 0.8, 0.2, 1);
  filter: brightness(0.85);
}

.video-card:hover .video-thumbnail img {
  transform: scale(1.05);
  filter: brightness(0.7);
}

.play-btn {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 90px;
  height: 90px;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  z-index: 2;
}

.play-btn::before {
  content: '';
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0.3);
  animation: ripple 2s infinite ease-out;
}

.play-btn svg {
  width: 40px;
  height: 40px;
  margin-left: 5px; 
  filter: drop-shadow(0 2px 5px rgba(0,0,0,0.3));
}

.play-btn:hover {
  background: var(--accent-primary);
  border-color: transparent;
  transform: translate(-50%, -50%) scale(1.1);
  box-shadow: 0 15px 30px rgba(138, 43, 226, 0.4);
}

.play-btn:hover::before {
  animation: none;
}

.video-details {
  padding: 3rem 2.5rem;
  text-align: center;
  background: rgba(255, 255, 255, 0.02);
}

.client-name {
  color: var(--accent-secondary);
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 3px;
  font-size: 0.85rem;
  display: block;
  margin-bottom: 0.8rem;
}

.video-title {
  font-size: 2.2rem;
  margin-bottom: 1.2rem;
  color: #fff;
  font-weight: 700;
}

.video-desc {
  color: var(--text-muted);
  max-width: 750px;
  margin: 0 auto;
  font-size: 1.1rem;
  line-height: 1.7;
}

@keyframes ripple {
  0% { transform: scale(1); opacity: 1; }
  100% { transform: scale(1.5); opacity: 0; }
}

@media (max-width: 768px) {
  .video-thumbnail {
    height: 300px;
  }
  .play-btn {
    width: 70px;
    height: 70px;
  }
  .video-title {
    font-size: 1.8rem;
  }
  .video-details {
    padding: 2rem 1.5rem;
  }
}
</style>
