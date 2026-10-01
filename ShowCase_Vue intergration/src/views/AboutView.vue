<template>
  <section class="about-section">
    <div class="about-container">
      <img
        src="/IMG_1209.jpg"
        alt="Profile Picture of Zaarah"
        class="about-image"
      />
      <div class="about-text">
        <h1>About Me</h1>
        <p>
          Hi, and welcome to my portfolio! I'm Zaarah, a beginner web
          developer with a passion for creativity and design. I started
          learning coding in 2022, and since then, I've been on an exciting
          journey of discovery and growth in the world of web development.
        </p>
        <p>
          My passion for coding began with a simple curiosity about how
          websites are built and how they work. As I delved deeper into HTML,
          CSS, and JavaScript, I found myself captivated by the endless
          possibilities of creating beautiful and functional websites.
        </p>
        <p>
          Outside of coding, I have a love for reading, art, and design. I
          believe creativity is a huge part of web development, and I aim to
          bring a unique and artistic touch to every project I create.
        </p>
        <a href="/UPdate CV.pdf" download>
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
.about-section {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 100px 20px;
  background: linear-gradient(135deg, #f5ebdd, #709a5f);
}

.about-container {
  max-width: 1100px;
  display: flex;
  align-items: center;
  gap: 50px;
  padding: 40px;
  border-radius: 25px;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.25);
  animation: fadeUp 1.5s ease;
}

.about-image {
  width: 320px;
  height: 320px;
  object-fit: cover;
  border-radius: 20px;
  border: 5px solid #f5ebdd;
  animation: floatLogo 4s ease-in-out infinite;
}

.about-text {
  flex: 1;
  background: #1f4f2b;
  padding: 30px;
  border-radius: 20px;
  color: white;
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
}

.about-text h1 {
  text-align: center;
  font-size: 3rem;
  margin-bottom: 20px;
}

.about-text p {
  line-height: 1.8;
  margin-bottom: 18px;
  font-size: 1.05rem;
}

.btn-download {
  padding: 14px 30px;
  border: none;
  border-radius: 30px;
  background-color: #1f4f2b;
  color: white;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 8px;
  margin: 20px auto 0;
  font-weight: 700;
}

.btn-download:hover {
  background-color: #6b4f3a;
  transform: translateY(-5px) scale(1.05);
}

.btn-download i {
  font-size: 1.1rem;
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
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-10px);
  }
  100% {
    transform: translateY(0px);
  }
}

@media (max-width: 768px) {
  .about-container {
    flex-direction: column;
    text-align: center;
  }

  .about-image {
    width: 250px;
    height: 250px;
  }

  .about-text h1 {
    font-size: 2.2rem;
  }
}
</style>