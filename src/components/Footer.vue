<script setup>
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="footer" id="contact">
    <div class="container">
      <div class="footer-content">
        <div class="footer-brand">
          <h2 class="logo text-gradient">PSS.</h2>
          <p class="footer-desc">
            Informatics Student & Visual Creator. Crafting beautiful, functional, and memorable digital experiences.
          </p>
        </div>
        
        <div class="footer-links">
          <h3>Get In Touch</h3>
          <ul>
            <li>
              <a href="mailto:putusanjayasamba@email.com">
                <span>Email</span>
                putusanjayasamba@email.com
              </a>
            </li>
            <li>
              <a href="https://github.com/putusanjayasamba" target="_blank">
                <span>GitHub</span>
                @putusanjayasamba
              </a>
            </li>
            <li>
              <a href="#">
                <span>Instagram</span>
                @putusanjaya.visuals
              </a>
            </li>
            <li>
              <a href="#">
                <span>LinkedIn</span>
                Putu Sanjaya Samba
              </a>
            </li>
          </ul>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; {{ currentYear }} Putu Sanjaya Samba. All rights reserved.</p>
        <p class="built-with">
          Built with <span class="vue-color">Vue.js</span> & Modern CSS
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: var(--bg-secondary);
  padding: 100px 0 40px;
  border-top: 1px solid rgba(255, 255, 255, 0.03);
  margin-top: 80px;
  position: relative;
  overflow: hidden;
}

.footer::before {
  content: '';
  position: absolute;
  top: 0; left: 50%;
  transform: translateX(-50%);
  width: 50%;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--accent-primary), transparent);
  opacity: 0.5;
}

.footer-content {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  gap: 5rem;
  margin-bottom: 5rem;
}

.logo {
  font-size: 3rem;
  font-weight: 800;
  margin-bottom: 1.5rem;
  letter-spacing: -2px;
}

.footer-desc {
  color: var(--text-muted);
  max-width: 450px;
  font-size: 1.1rem;
  line-height: 1.8;
}

.footer-links h3 {
  font-size: 1.3rem;
  margin-bottom: 2rem;
  color: #fff;
  font-weight: 600;
  letter-spacing: 1px;
}

.footer-links ul {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.footer-links a {
  display: flex;
  flex-direction: column;
  color: var(--text-muted);
  transition: all 0.3s ease;
  font-size: 1.05rem;
}

.footer-links a span {
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 1.5px;
  color: rgba(255, 255, 255, 0.3);
  margin-bottom: 0.3rem;
  font-weight: 600;
}

.footer-links a:hover {
  color: #fff;
  transform: translateX(5px);
}

.footer-links a:hover span {
  color: var(--accent-secondary);
}

.footer-bottom {
  padding-top: 2.5rem;
  border-top: 1px solid rgba(255, 255, 255, 0.05);
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: rgba(255, 255, 255, 0.4);
  font-size: 0.95rem;
}

.vue-color {
  color: #4FC08D;
  font-weight: 600;
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }
  .footer-bottom {
    flex-direction: column;
    text-align: center;
    gap: 1.5rem;
  }
}
</style>
