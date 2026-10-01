<template>
  <section class="hero">
    <video autoplay muted loop playsinline class="bg-video">
      <source src="/HTML & CSS.mp4" type="video/mp4" />
    </video>
    <div class="overlay"></div>
    <div class="hero-content">
      <h1>My Coding Journey</h1>
      <p>Creative Beginner Developer • Dreamer • Designer</p>
      <p class="hero-subtitle">Building beautiful websites with passion and creativity</p>
      <router-link to="/projects" class="cta-button">
        <i class="fas fa-arrow-right"></i> View My Projects
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
  padding: 20px;
  animation: fadeUp 1.5s ease;
}

.hero h1 {
  font-size: 4rem;
  margin-bottom: 20px;
}

.hero p {
  font-size: 1.3rem;
  margin-bottom: 30px;
}

.hero-subtitle {
  font-size: 1.1rem;
  margin-bottom: 30px;
  opacity: 0.9;
}

.cta-button {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 14px 30px;
  border: none;
  border-radius: 30px;
  background-color: #1f4f2b;
  color: white;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
  font-weight: 700;
}

.cta-button:hover {
  background-color: #6b4f3a;
  transform: translateY(-5px) scale(1.05);
}

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

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2.7rem;
  }

  .hero p {
    font-size: 1rem;
  }
}
</style>