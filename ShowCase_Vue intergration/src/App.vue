<template>
  <div id="app">
    <!-- NAVIGATION -->
    <nav aria-label="Main navigation">
      <div class="nav-logo">Zaarah's Portfolio</div>
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
        <h3>Zaarah Okkers</h3>
        <p class="footer-text">
          Web Developer • Designer • Creative Thinker
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
          <a href="https://github.com/Zaarah-Okkers" target="_blank" rel="noopener noreferrer">
            <i class="fas fa-github"></i> GitHub
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
        { name: 'About', path: '/about', icon: 'fas fa-user' },
        { name: 'Projects', path: '/projects', icon: 'fas fa-briefcase' },
        { name: 'Contact', path: '/contact', icon: 'fas fa-envelope' }
      ]
    }
  }
}
</script>

<style>
:root {
  --forest-green: #1f4f2b;
  --cream: #f5ebdd;
  --warm-brown: #6b4f3a;
  --soft-white: #ffffff;
  --accent: #d4a373;
  --darkseagreen: #709a5f;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: Arial, sans-serif;
  background-color: var(--cream);
  overflow-x: hidden;
}

img {
  max-width: 100%;
  display: block;
}

/* NAVIGATION */
nav {
  background: rgba(31, 79, 43, 0.95);
  backdrop-filter: blur(8px);
  padding: 1rem 2rem;
  position: sticky;
  top: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  z-index: 1000;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  flex-wrap: wrap;
}

.nav-logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--cream);
  margin-right: 1rem;
  white-space: nowrap;
}

nav a {
  color: var(--cream);
  text-decoration: none;
  font-weight: 600;
  padding: 8px 14px;
  border: 2px solid transparent;
  border-radius: 8px;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 6px;
}

nav a i {
  font-size: 1.2rem;
}

nav a:hover {
  background-color: var(--warm-brown);
  border-color: var(--warm-brown);
  transform: translateY(-3px);
}

nav a.active {
  background-color: var(--warm-brown);
}

/* FOOTER */
.footer {
  background: var(--forest-green);
  padding: 13px 15px 12px;
  text-align: center;
  border-top: 3px solid var(--accent);
  margin-top: 25px;
}

.footer-content {
  max-width: 900px;
  margin: 0 auto;
}

.footer h3 {
  color: white;
  font-size: 1.7rem;
  margin-bottom: 5px;
}

.footer-text {
  color: var(--cream);
  font-size: 0.95rem;
  line-height: 1.3;
  margin-bottom: 12px;
}

.footer-links {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 12px;
}

.footer-links a {
  color: white;
  text-decoration: none;
  font-size: 0.9rem;
  transition: 0.3s ease;
  display: flex;
  align-items: center;
  gap: 6px;
}

.footer-links a i {
  font-size: 1.1rem;
}

.footer-links a:hover {
  color: var(--accent);
}

.footer-links span {
  color: rgba(255, 255, 255, 0.4);
}

.footer-line {
  width: 85%;
  height: 1px;
  background: rgba(255, 255, 255, 0.2);
  margin: 0 auto 10px;
}

.copyright {
  color: rgba(255, 255, 255, 0.7);
  font-size: 0.8rem;
}

a:focus-visible,
button:focus-visible,
input:focus-visible,
textarea:focus-visible {
  outline: 3px solid var(--accent);
  outline-offset: 3px;
}

@media (max-width: 768px) {
  nav {
    flex-wrap: wrap;
    padding: 1rem;
  }

  nav a {
    font-size: 0.9rem;
  }
}
</style>