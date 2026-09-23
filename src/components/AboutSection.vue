<script setup>
const skills = [
  { 
    name: 'HTML5', 
    icon: '<svg viewBox="0 0 24 24" width="32" height="32" stroke="currentColor" stroke-width="2" fill="none"><path d="M4 4l2 14.5L12 21l6-2.5L20 4H4zm12.5 4H8.5L9 11.5h7l-.5 4.5-3.5 1-3.5-1-.25-2.5H6.5l.5 4.5 5 1.5 5-1.5.75-6.5H9.5L9 9h8.5l-.5-1z"/></svg>',
    color: '#E34F26'
  },
  { 
    name: 'CSS3', 
    icon: '<svg viewBox="0 0 24 24" width="32" height="32" stroke="currentColor" stroke-width="2" fill="none"><path d="M4 4l2 14.5L12 21l6-2.5L20 4H4zm12.5 4H8.5L9 11.5h7l-.5 4.5-3.5 1-3.5-1-.25-2.5H6.5l.5 4.5 5 1.5 5-1.5.75-6.5H9.5L9 9h8.5l-.5-1z"/></svg>',
    color: '#1572B6'
  },
  { 
    name: 'JavaScript', 
    icon: '<svg viewBox="0 0 24 24" width="32" height="32" stroke="currentColor" stroke-width="2" fill="none"><rect x="4" y="4" width="16" height="16" rx="2" ry="2"></rect><path d="M8 17.5c-1 0-1.5-.5-1.5-1.5M10.5 16v1.5c0 1.5-1 2.5-2.5 2.5h-1M18.5 17c0 1.5-1.5 2.5-3 2.5-1 0-2-.5-2.5-1.5M15.5 12c-1.5 0-2.5.5-2.5 1.5s1 1.5 2.5 1.5 2.5 1 2.5 2.5-1 2.5-2.5 2.5"></path></svg>',
    color: '#F7DF1E'
  },
  { 
    name: 'Vue.js', 
    icon: '<svg viewBox="0 0 24 24" width="32" height="32" stroke="currentColor" stroke-width="2" fill="none"><path d="M12 2L2 22h20L12 2z"></path><path d="M12 10L6.5 22h11L12 10z"></path></svg>',
    color: '#4FC08D'
  },
  { 
    name: 'Figma', 
    icon: '<svg viewBox="0 0 24 24" width="32" height="32" stroke="currentColor" stroke-width="2" fill="none"><path d="M5 5.5A3.5 3.5 0 0 1 8.5 2h7A3.5 3.5 0 0 1 19 5.5v13a3.5 3.5 0 0 1-3.5 3.5h-7A3.5 3.5 0 0 1 5 18.5v-13z"></path><circle cx="12" cy="12" r="3.5"></circle></svg>',
    color: '#F24E1E'
  },
  { 
    name: 'Photography', 
    icon: '<svg viewBox="0 0 24 24" width="32" height="32" stroke="currentColor" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"></path><circle cx="12" cy="13" r="4"></circle></svg>',
    color: '#E0E0E0'
  },
  { 
    name: 'Videography', 
    icon: '<svg viewBox="0 0 24 24" width="32" height="32" stroke="currentColor" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"><polygon points="23 7 16 12 23 17 23 7"></polygon><rect x="1" y="5" width="15" height="14" rx="2" ry="2"></rect></svg>',
    color: '#E0E0E0'
  }
]
</script>

<template>
  <section class="section">
    <div class="container">
      <h2 class="section-title">About Me</h2>
      
      <div class="about-grid">
        <div class="glass-card about-content">
          <h3 class="card-title">Brief Profile</h3>
          <p class="about-text">
            I am an Informatics student at <strong>Primakara University</strong>. 
            My passion lies in front-end web development and user interface design (UI/UX).
            I strive to create digital experiences that are both functionally robust and visually engaging.
          </p>
          <p class="about-text mt-4">
            Beyond the screen, I am a passionate visual creator, capturing and directing 
            beautiful moments, specializing in Wedding Documentation in Bali.
            I believe that the analytical mindset of programming and the aesthetic eye of visual arts 
            complement each other beautifully to build stunning web interfaces.
          </p>
        </div>
        
        <div class="glass-card skills-content">
          <h3 class="card-title">Tech Stack & Skills</h3>
          <div class="skills-grid">
            <div v-for="skill in skills" :key="skill.name" class="skill-box">
              <div class="skill-icon" v-html="skill.icon" :style="{ color: skill.color }"></div>
              <span class="skill-name">{{ skill.name }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  gap: 3rem;
}

.about-content, .skills-content {
  padding: 3rem;
}

.card-title {
  font-size: 1.8rem;
  margin-bottom: 1.5rem;
  color: var(--text-main);
  font-weight: 700;
  letter-spacing: 0.5px;
}

.about-text {
  font-size: 1.1rem;
  color: var(--text-muted);
  line-height: 1.8;
}

.mt-4 {
  margin-top: 1.5rem;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.skill-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 1.5rem 1rem;
  background: rgba(255, 255, 255, 0.02);
  border: 1px solid rgba(255, 255, 255, 0.05);
  border-radius: 16px;
  transition: all 0.3s ease;
  cursor: pointer;
}

.skill-box:hover {
  background: rgba(255, 255, 255, 0.05);
  transform: translateY(-5px);
  border-color: rgba(255, 255, 255, 0.15);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.skill-icon {
  margin-bottom: 0.8rem;
  display: flex;
  justify-content: center;
  align-items: center;
  filter: drop-shadow(0 0 8px currentColor);
  transition: transform 0.3s ease;
}

.skill-box:hover .skill-icon {
  transform: scale(1.1);
}

.skill-name {
  font-size: 0.85rem;
  font-weight: 500;
  color: var(--text-muted);
  text-align: center;
}

@media (max-width: 992px) {
  .about-grid {
    grid-template-columns: 1fr;
  }
}
</style>
