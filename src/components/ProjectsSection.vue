<script setup>
const projects = [
  {
    id: 1,
    title: 'Vidiomate',
    category: 'Photographer Platform',
    description: 'A specialized platform for photographers to showcase portfolios, manage booking schedules, and interact with clients seamlessly.',
    tech: ['Vue.js', 'Tailwind', 'Node.js'],
    image: 'https://images.unsplash.com/photo-1542038784456-1ea8e935640e?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
    link: '#'
  },
  {
    id: 2,
    title: 'The Prada Puri Bali',
    category: 'E-Commerce',
    description: 'A premium online store for The Prada Puri Bali featuring an elegant shopping cart and exclusive product management.',
    tech: ['Vue.js', 'Vuex', 'CSS Modules'],
    image: 'https://images.unsplash.com/photo-1607082348824-0a96f2a4b9da?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
    link: '#'
  },
  {
    id: 3,
    title: 'UMKM Web Portal',
    category: 'Information System',
    description: 'A web application empowering local MSMEs (UMKM) to digitize their business, from company profiles to digital product catalogs.',
    tech: ['HTML', 'CSS', 'JavaScript'],
    image: 'https://images.unsplash.com/photo-1472851294608-062f824d29cc?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80',
    link: '#'
  }
]
</script>

<template>
  <section class="section">
    <div class="container">
      <h2 class="section-title">Web Projects</h2>
      
      <div class="projects-grid">
        <div v-for="project in projects" :key="project.id" class="project-card glass-card">
          <div class="project-image">
            <img :src="project.image" :alt="project.title" />
            <div class="project-overlay">
              <a :href="project.link" class="btn btn-primary btn-sm">View Details</a>
            </div>
          </div>
          
          <div class="project-info">
            <div class="project-header">
              <span class="project-category">{{ project.category }}</span>
            </div>
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-desc">{{ project.description }}</p>
            
            <div class="project-tech">
              <span v-for="tech in project.tech" :key="tech" class="tech-tag">
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
  gap: 3rem;
}

.project-card {
  padding: 0;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  border-radius: 24px;
  background: rgba(255, 255, 255, 0.015);
  border: 1px solid rgba(255, 255, 255, 0.04);
}

.project-image {
  position: relative;
  height: 240px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.6s cubic-bezier(0.2, 0.8, 0.2, 1);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(10, 10, 12, 0.85);
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  backdrop-filter: blur(4px);
  transition: all 0.4s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.08);
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-info {
  padding: 2rem;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.project-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.8rem;
}

.project-category {
  font-size: 0.8rem;
  color: var(--accent-secondary);
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1.5px;
}

.project-title {
  font-size: 1.6rem;
  margin-bottom: 1rem;
  color: #fff;
  font-weight: 700;
}

.project-desc {
  font-size: 1rem;
  color: var(--text-muted);
  margin-bottom: 2rem;
  line-height: 1.6;
  flex-grow: 1;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
}

.tech-tag {
  font-size: 0.8rem;
  padding: 0.4rem 1rem;
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 30px;
  color: var(--text-main);
  font-weight: 500;
  transition: all 0.3s ease;
}

.project-card:hover .tech-tag {
  background: rgba(138, 43, 226, 0.1);
  border-color: rgba(138, 43, 226, 0.3);
  color: #fff;
}
</style>
