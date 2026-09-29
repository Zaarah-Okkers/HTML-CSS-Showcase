<template>
  <section class="hero">
    <video autoplay muted loop playsinline class="bg-video">
      <source src="/HTML & CSS.mp4" type="video/mp4" />
    </video>
    <div class="overlay"></div>
    <div class="hero-content">
      <div class="hero-greeting">
        <i class="fas fa-star"></i>
        <i class="fas fa-heart"></i>
        <i class="fas fa-star"></i>
      </div>
      <h1>Hi, I'm Zaarah Okkers</h1>
      <p>Aspiring Full Stack Developer</p>
      <p class="hero-subtitle">
        I'm looking for a full stack developer role where I can build complete, responsive web applications from the interface to the backend.
      </p>
      <router-link to="/projects" class="cta-button">
        <i class="fas fa-arrow-right"></i> View My Work
      </router-link>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HomeView'
}
</script>

<style scoped>
:root {
  --hello-kitty-pink: #ffb6d9;
  --hello-kitty-light-pink: #ffd4e5;
  --hello-kitty-red: #ff1493;
  --hello-kitty-white: #ffffff;
  --hello-kitty-cream: #fffacd;
  --hello-kitty-purple: #dda0dd;
  --hello-kitty-blue: #add8e6;
}

.hero {
  position: relative;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  overflow: hidden;
  color: white;
}

.bg-video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: 0;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.45);
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 2;
  max-width: 700px;
  padding: 40px 20px;
  animation: fadeUp 1.5s ease;
  background: rgba(255, 182, 217, 0.12);
  backdrop-filter: blur(8px);
  border-radius: 30px;
  border: 2px solid rgba(255, 255, 255, 0.25);
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15);
}

.hero-greeting {
  font-size: 2rem;
  margin-bottom: 20px;
  animation: bounce 2s ease-in-out infinite;
}

.hero-greeting i {
  margin: 0 10px;
  color: #ffff00;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
}

.hero h1 {
  font-size: 4rem;
  margin-bottom: 20px;
  color: #ffff00;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.4);
  font-weight: 900;
}

.hero p {
  font-size: 1.3rem;
  margin-bottom: 15px;
  color: white;
  text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
}

.hero-subtitle {
  font-size: 1.1rem;
  margin-bottom: 30px;
  color: var(--hello-kitty-cream);
}

.hero-subtitle i {
  margin-left: 8px;
}

.cta-button {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 16px 40px;
  border: none;
  border-radius: 50px;
  background: linear-gradient(135deg, var(--hello-kitty-red) 0%, #ff69b4 100%);
  color: white;
  font-size: 1.1rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
  box-shadow: 0 6px 16px rgba(255, 20, 147, 0.3);
  border: 2px solid white;
}

.cta-button:hover {
  background: linear-gradient(135deg, #ff69b4 0%, var(--hello-kitty-red) 100%);
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(255, 20, 147, 0.4);
}

.cta-button i {
  font-size: 1.2rem;
  animation: slideRight 0.6s ease-in-out infinite;
}

/* ANIMATIONS */
@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-15px);
  }
}

@keyframes slideRight {
  0%, 100% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(8px);
  }
}

@media (max-width: 768px) {
  .hero-content {
    padding: 30px 15px;
    border-radius: 20px;
  }

  .hero h1 {
    font-size: 2.7rem;
  }

  .hero p {
    font-size: 1rem;
  }

  .cta-button {
    padding: 12px 30px;
    font-size: 0.95rem;
  }
}
</style>