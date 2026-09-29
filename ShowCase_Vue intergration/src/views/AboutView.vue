<template>
  <section class="about-section">
    <div class="about-container">
      <div class="about-image-wrapper">
        <img
          src="/IMG_1209.jpg"
          alt="Profile Picture of Zaarah"
          class="about-image"
        />
        <div class="image-decoration">
          <i class="fas fa-star"></i>
          <i class="fas fa-heart"></i>
          <i class="fas fa-star"></i>
        </div>
      </div>
      <div class="about-text">
        <div class="about-header">
          <i class="fas fa-user-circle"></i>
          <h1>About Me</h1>
          <i class="fas fa-user-circle"></i>
        </div>
        
        <p>
          <i class="fas fa-lightbulb"></i>
          Hi, and welcome to my portfolio! I'm Zaarah, a beginner web
          developer with a passion for creativity and design. I started
          learning coding in 2022, and since then, I've been on an exciting
          journey of discovery and growth in the world of web development.
        </p>

        <p>
          <i class="fas fa-code"></i>
          My passion for coding began with a simple curiosity about how
          websites are built and how they work. As I delved deeper into HTML,
          CSS, and JavaScript, I found myself captivated by the endless
          possibilities of creating beautiful and functional websites.
        </p>

        <p>
          <i class="fas fa-palette"></i>
          Outside of coding, I have a love for reading, art, and design. I
          believe creativity is a huge part of web development, and I aim to
          bring a unique and artistic touch to every project I create.
        </p>

        <div class="skills-section">
          <h3>
            <i class="fas fa-rocket"></i> My Skills
          </h3>
          <div class="skills-grid">
            <div class="skill-tag">HTML</div>
            <div class="skill-tag">CSS</div>
            <div class="skill-tag">JavaScript</div>
            <div class="skill-tag">Vue.js</div>
            <div class="skill-tag">Python</div>
            <div class="skill-tag">Web Design</div>
          </div>
        </div>

        <a href="/UPdate CV.pdf" download class="cv-download">
          <button class="btn-download">
            <i class="fas fa-download"></i> Download CV
          </button>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutView'
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

.about-section {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 100px 20px;
  background: linear-gradient(135deg, var(--hello-kitty-cream) 0%, var(--hello-kitty-light-pink) 100%);
  background-attachment: fixed;
  position: relative;
}

.about-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    repeating-linear-gradient(45deg, transparent, transparent 35px, rgba(255, 182, 217, 0.03) 35px, rgba(255, 182, 217, 0.03) 70px),
    repeating-linear-gradient(-45deg, transparent, transparent 35px, rgba(221, 160, 221, 0.03) 35px, rgba(221, 160, 221, 0.03) 70px);
  pointer-events: none;
  z-index: 0;
}

.about-container {
  max-width: 1100px;
  display: flex;
  align-items: center;
  gap: 50px;
  padding: 50px;
  border-radius: 30px;
  background: rgba(255, 255, 255, 0.12);
  box-shadow: 0 8px 24px rgba(255, 20, 147, 0.15);
  animation: fadeUp 1.5s ease;
  position: relative;
  z-index: 1;
  border: 2px solid rgba(255, 255, 255, 0.25);
}

.about-image-wrapper {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.about-image {
  width: 320px;
  height: 320px;
  object-fit: cover;
  border-radius: 20px;
  border: 5px solid var(--hello-kitty-pink);
  animation: floatLogo 4s ease-in-out infinite;
  box-shadow: 0 8px 20px rgba(255, 20, 147, 0.2);
}

.image-decoration {
  position: absolute;
  top: -20px;
  right: -20px;
  font-size: 2rem;
  display: flex;
  gap: 10px;
  color: var(--hello-kitty-red);
  animation: bounce 2s ease-in-out infinite;
}

.about-text {
  flex: 1;
  background: linear-gradient(135deg, var(--hello-kitty-pink) 0%, #ff69b4 100%);
  padding: 40px;
  border-radius: 25px;
  color: white;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  position: relative;
}

.about-text::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: 
    repeating-linear-gradient(45deg, transparent, transparent 20px, rgba(255, 255, 255, 0.02) 20px, rgba(255, 255, 255, 0.02) 40px);
  border-radius: 25px;
  pointer-events: none;
}

.about-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 15px;
  margin-bottom: 25px;
  position: relative;
  z-index: 1;
}

.about-header i {
  font-size: 2rem;
  animation: bounce 1.5s ease-in-out infinite;
}

.about-header h1 {
  text-align: center;
  font-size: 3rem;
  margin-bottom: 0;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
}

.about-text p {
  line-height: 1.8;
  margin-bottom: 20px;
  font-size: 1.05rem;
  position: relative;
  z-index: 1;
}

.about-text p i {
  margin-right: 10px;
  font-size: 1.2rem;
  color: var(--hello-kitty-cream);
}

.skills-section {
  margin: 30px 0;
  padding: 20px;
  background: rgba(255, 255, 255, 0.12);
  border-radius: 15px;
  position: relative;
  z-index: 1;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.skills-section h3 {
  margin-bottom: 15px;
  font-size: 1.3rem;
  display: flex;
  align-items: center;
  gap: 10px;
}

.skills-section h3 i {
  font-size: 1.5rem;
  animation: bounce 2s ease-in-out infinite;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  gap: 10px;
}

.skill-tag {
  background: rgba(255, 255, 255, 0.2);
  padding: 10px 15px;
  border-radius: 20px;
  border: 2px solid white;
  font-weight: 600;
  text-align: center;
  transition: all 0.3s ease;
  cursor: default;
}

.skill-tag:hover {
  background: white;
  color: var(--hello-kitty-red);
  transform: translateY(-3px);
  box-shadow: 0 4px 12px rgba(255, 20, 147, 0.2);
}

.cv-download {
  display: flex;
  justify-content: center;
  margin-top: 25px;
  position: relative;
  z-index: 1;
}

.btn-download {
  padding: 14px 35px;
  border: 2px solid white;
  border-radius: 30px;
  background: rgba(255, 255, 255, 0.2);
  color: white;
  font-size: 1rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 10px;
}

.btn-download:hover {
  background: white;
  color: var(--hello-kitty-red);
  transform: translateY(-5px);
  box-shadow: 0 6px 16px rgba(255, 255, 255, 0.3);
}

.btn-download i {
  font-size: 1.2rem;
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

@keyframes floatLogo {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-15px);
  }
}

@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

@media (max-width: 768px) {
  .about-container {
    flex-direction: column;
    text-align: center;
    padding: 30px;
    gap: 30px;
  }

  .about-image {
    width: 250px;
    height: 250px;
  }

  .about-text {
    padding: 30px 20px;
  }

  .about-header h1 {
    font-size: 2.2rem;
  }

  .skills-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>