<template>
  <div id="app">
    <!-- NAVIGATION -->
    <nav aria-label="Main navigation">
      <div class="nav-logo">
        <div class="bow">🎀</div>
        Zaarah's Portfolio
      </div>
      <router-link 
        v-for="link in navLinks" 
        :key="link.path"
        :to="link.path"
        :class="{ active: $route.path === link.path }"
      >
        <i :class="link.icon"></i> {{ link.name }}
      </router-link>
    </nav>

    <!-- PAGE CONTENT -->
    <router-view></router-view>

    <!-- FOOTER -->
    <footer class="footer">
      <div class="footer-content">
        <h3>✧ Zaarah Okkers ✧</h3>
        <p class="footer-text">
          Creative Developer • Dreamer • Designer
        </p>
        <div class="footer-links">
          <a href="mailto:zaarahokkers@gmail.com">
            <i class="fas fa-envelope"></i> Email
          </a>
          <span>•</span>
          <a href="https://www.linkedin.com/in/zaarah-okkers-3688b1377" target="_blank" rel="noopener noreferrer">
            <i class="fas fa-briefcase"></i> LinkedIn
          </a>
          <span>•</span>
          <a href="https://www.lifechoicesacademy.com" target="_blank" rel="noopener noreferrer">
            <i class="fas fa-map-marker-alt"></i> Cape Town
          </a>
        </div>
        <div class="footer-line"></div>
        <p class="copyright">© 2026 Zaarah Okkers | All Rights Reserved</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      navLinks: [
        { name: 'Home', path: '/', icon: 'fas fa-home' },
        { name: 'About', path: '/about', icon: 'fas fa-user-circle' },
        { name: 'Projects', path: '/projects', icon: 'fas fa-star' },
        { name: 'Skills', path: '/skills', icon: 'fas fa-rocket' },
        { name: 'Resume', path: '/resume', icon: 'fas fa-file-alt' },
        { name: 'Testimonials', path: '/testimonials', icon: 'fas fa-quote-right' },
        { name: 'Contact', path: '/contact', icon: 'fas fa-envelope-open' }
      ]
    }
  }
}
</script>
<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Arial', 'Helvetica', sans-serif;
  background: linear-gradient(135deg, #ffffff 0%, #ffe0ec 100%);
  background-attachment: fixed;
  overflow-x: hidden;
  min-height: 100vh;
}

img {
  max-width: 100%;
  display: block;
  border-radius: 15px;
}

/* NAVIGATION */
nav {
  background: linear-gradient(135deg, #ff69b4 0%, #ff1493 100%);
  padding: 1.2rem 2rem;
  position: sticky;
  top: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2.5rem;
  z-index: 1000;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  flex-wrap: wrap;
  border-bottom: 3px solid white;
}

.nav-logo {
  font-size: 1.4rem;
  font-weight: bold;
  color: white;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
  margin-right: 1rem;
  white-space: nowrap;
  display: flex;
  align-items: center;
  gap: 8px;
}

.bow {
  font-size: 1.5rem;
  animation: wiggle 1s ease-in-out infinite;
}

nav a {
  color: white;
  text-decoration: none;
  font-weight: 700;
  padding: 10px 20px;
  border: 2px solid white;
  border-radius: 20px;
  transition: all 0.3s ease;
  font-size: 1rem;
  background: rgba(255, 255, 255, 0.15);
  display: flex;
  align-items: center;
  gap: 8px;
}

nav a i {
  font-size: 1.2rem;
}

nav a:hover {
  background: white;
  color: #ff1493;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(255, 255, 255, 0.4);
}

nav a.active {
  background: white;
  color: #ff1493;
  border-color: white;
}

/* FOOTER */
.footer {
  background: linear-gradient(135deg, #ff69b4 0%, #ff1493 100%);
  padding: 30px 20px;
  text-align: center;
  border-top: 3px solid white;
  margin-top: 60px;
}

.footer-content {
  max-width: 900px;
  margin: 0 auto;
}

.footer h3 {
  color: white;
  font-size: 1.8rem;
  margin-bottom: 10px;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
}

.footer-text {
  color: white;
  font-size: 0.95rem;
  line-height: 1.5;
  margin-bottom: 15px;
  font-weight: 600;
}

.footer-links {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 15px;
}

.footer-links a {
  color: white;
  text-decoration: none;
  font-size: 0.95rem;
  transition: 0.3s ease;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 6px;
}

.footer-links a i {
  font-size: 1.1rem;
}

.footer-links a:hover {
  text-decoration: underline;
  transform: scale(1.05);
}

.footer-links span {
  color: white;
  font-weight: bold;
}

.footer-line {
  width: 80%;
  height: 2px;
  background: white;
  margin: 15px auto;
  border-radius: 2px;
}

.copyright {
  color: white;
  font-size: 0.85rem;
  font-weight: 600;
}

a:focus-visible,
button:focus-visible,
input:focus-visible,
textarea:focus-visible {
  outline: 3px solid #ff1493;
  outline-offset: 3px;
}

@keyframes wiggle {
  0%, 100% {
    transform: rotate(0deg);
  }
  25% {
    transform: rotate(-5deg);
  }
  75% {
    transform: rotate(5deg);
  }
}

@media (max-width: 768px) {
  nav {
    gap: 1rem;
  }

  .nav-logo {
    width: 100%;
    text-align: center;
    margin-right: 0;
    margin-bottom: 1rem;
    font-size: 1.2rem;
  }

  nav a {
    font-size: 0.9rem;
    padding: 8px 15px;
  }

  .footer h3 {
    font-size: 1.4rem;
  }
}
</style>