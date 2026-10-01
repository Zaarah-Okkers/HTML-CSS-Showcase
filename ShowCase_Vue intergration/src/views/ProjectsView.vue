<template>
  <section class="showcase-section">
    <h1 class="title">My Work & Achievements</h1>
    
    <!-- PROJECTS SECTION -->
    <div class="section-divider">
      <h2 class="section-title">Projects</h2>
    </div>
    <div class="projects-container">
      <div v-for="project in projects" :key="project.id" class="project-card">
        <img :src="project.image" :alt="project.title" />
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <a :href="project.link" target="_blank" rel="noopener noreferrer">
          <button class="btn-view">View Project</button>
        </a>
      </div>
    </div>

    <!-- CERTIFICATIONS SECTION -->
    <div class="section-divider">
      <h2 class="section-title">Certifications & Achievements</h2>
    </div>
    <div class="certifications-container">
      <div v-for="cert in certifications" :key="cert.id" class="cert-card">
        <div class="cert-icon">
          <i :class="cert.icon"></i>
        </div>
        <h3>{{ cert.title }}</h3>
        <p class="cert-issuer">{{ cert.issuer }}</p>
        <p class="cert-description">{{ cert.description }}</p>
        <a v-if="cert.link" :href="cert.link" target="_blank" rel="noopener noreferrer">
          <button class="btn-view">View Certificate</button>
        </a>
      </div>
    </div>

    <!-- SOCIAL & LINKS SECTION -->
    <div class="section-divider">
      <h2 class="section-title">Connect With Me</h2>
    </div>
    <div class="social-container">
      <div v-for="social in socialLinks" :key="social.id" class="social-card">
        <div class="social-icon">
          <i :class="social.icon"></i>
        </div>
        <h3>{{ social.title }}</h3>
        <p>{{ social.description }}</p>
        <a :href="social.link" target="_blank" rel="noopener noreferrer">
          <button class="btn-view">Visit</button>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProjectsView',
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'CampusSwap',
          description: 'A full-stack academic marketplace platform built with Vue.js, HTML, and CSS. Connect with students to buy, sell, and exchange academic materials and resources on campus.',
          image: '/Novel Nest (1).jpg',
          link: 'https://campusswap-fontend.onrender.com'
        },
        {
          id: 2,
          title: 'Python Mini Toolkit',
          description: 'A mini toolkit built with Python for handling common beginner coding tasks and exercises.',
          image: '/github.png',
          link: 'https://github.com/Zaarah-Okkers'
        },
        {
          id: 3,
          title: 'Novel Nest',
          description: 'A creative website project showcasing branding, layout design, and responsive web development skills.',
          image: '/Novel Nest (1).jpg',
          link: './Novel Nest/Index.html'
        },
        {
          id: 4,
          title: 'HTML & CSS Showcase',
          description: 'A modern showcase website highlighting my front-end development and styling skills.',
          image: '/Screenshot 2026-05-29 112635.png',
          link: 'https://github.com/Zaarah-Okkers'
        }
      ],
      certifications: [
        {
          id: 1,
          title: 'Certificate of Achievement - Research',
          issuer: 'GRIT - Gender Rights in Tech',
          description: 'Recognized for commitment to research and advancing gender equality in the tech industry.',
          icon: 'fas fa-certificate',
          link: 'https://www.linkedin.com/company/grit-gbvsouthafrica/'
        },
        {
          id: 2,
          title: 'Web Development Trainee',
          issuer: 'Life Choices Academy',
          description: 'Completed structured full-stack web development program covering HTML, CSS, JavaScript, and Vue.js.',
          icon: 'fas fa-graduation-cap',
          link: null
        }
      ],
      socialLinks: [
        {
          id: 1,
          title: 'HRFlow Platform',
          description: 'Explore my profile on the HRFlow talent platform.',
          icon: 'fas fa-briefcase',
          link: 'https://hrflow-xg3y.onrender.com'
        },
        {
          id: 2,
          title: 'LinkedIn Profile',
          description: 'Connect with me on LinkedIn and view my professional network.',
          icon: 'fas fa-linkedin',
          link: 'https://lnkd.in/dHsmYmsR'
        },
        {
          id: 3,
          title: 'LinkedIn Article',
          description: 'Read my insights and articles on LinkedIn.',
          icon: 'fas fa-newspaper',
          link: 'https://lnkd.in/dXM6X-5z'
        }
      ]
    }
  }
}
</script>

<style scoped>
.showcase-section {
  min-height: 100vh;
  padding: 100px 20px;
  background: linear-gradient(135deg, #f5ebdd, #709a5f);
  text-align: center;
}

.title {
  font-size: 3rem;
  color: #1f4f2b;
  margin-bottom: 50px;
  animation: slideDown 1.5s ease;
}

.section-divider {
  margin: 60px 0 40px;
}

.section-title {
  font-size: 2rem;
  color: #1f4f2b;
  padding-bottom: 15px;
  border-bottom: 3px solid #6b4f3a;
  display: inline-block;
}

/* PROJECTS SECTION */
.projects-container {
  display: flex;
  justify-content: center;
  gap: 35px;
  flex-wrap: wrap;
  margin-bottom: 40px;
}

.project-card {
  width: 320px;
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(12px);
  border-radius: 25px;
  overflow: hidden;
  padding-bottom: 25px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
  transition: all 0.4s ease;
  animation: fadeUp 1s ease;
}

.project-card:hover {
  transform: translateY(-12px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.35);
}

.project-card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.project-card:hover img {
  transform: scale(1.05);
}

.project-card h3 {
  margin: 20px 0 10px;
  color: white;
}

.project-card p {
  padding: 0 20px;
  line-height: 1.6;
  color: #f5ebdd;
  margin-bottom: 20px;
}

/* CERTIFICATIONS SECTION */
.certifications-container {
  display: flex;
  justify-content: center;
  gap: 35px;
  flex-wrap: wrap;
  margin-bottom: 40px;
}

.cert-card {
  width: 320px;
  background: linear-gradient(135deg, rgba(31, 79, 43, 0.2), rgba(107, 79, 58, 0.2));
  backdrop-filter: blur(12px);
  border-radius: 25px;
  padding: 30px 25px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
  transition: all 0.4s ease;
  animation: fadeUp 1.2s ease;
  border: 2px solid rgba(212, 163, 115, 0.3);
}

.cert-card:hover {
  transform: translateY(-12px);
  background: linear-gradient(135deg, rgba(31, 79, 43, 0.3), rgba(107, 79, 58, 0.3));
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.25);
  border-color: rgba(212, 163, 115, 0.6);
}

.cert-icon {
  font-size: 3rem;
  color: #1f4f2b;
  margin-bottom: 15px;
  animation: bounce 2s ease-in-out infinite;
}

.cert-card h3 {
  color: #1f4f2b;
  margin-bottom: 8px;
  font-size: 1.2rem;
}

.cert-issuer {
  color: #6b4f3a;
  font-weight: 700;
  margin-bottom: 10px;
  font-size: 0.95rem;
}

.cert-description {
  color: #1f4f2b;
  line-height: 1.6;
  margin-bottom: 20px;
  font-size: 0.95rem;
}

/* SOCIAL SECTION */
.social-container {
  display: flex;
  justify-content: center;
  gap: 35px;
  flex-wrap: wrap;
}

.social-card {
  width: 320px;
  background: linear-gradient(135deg, rgba(107, 79, 58, 0.2), rgba(31, 79, 43, 0.2));
  backdrop-filter: blur(12px);
  border-radius: 25px;
  padding: 30px 25px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
  transition: all 0.4s ease;
  animation: fadeUp 1.4s ease;
  border: 2px solid rgba(107, 79, 58, 0.3);
}

.social-card:hover {
  transform: translateY(-12px);
  background: linear-gradient(135deg, rgba(107, 79, 58, 0.3), rgba(31, 79, 43, 0.3));
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.25);
  border-color: rgba(107, 79, 58, 0.6);
}

.social-icon {
  font-size: 3rem;
  color: #6b4f3a;
  margin-bottom: 15px;
  animation: bounce 2s ease-in-out infinite;
}

.social-card h3 {
  color: #1f4f2b;
  margin-bottom: 8px;
  font-size: 1.2rem;
}

.social-card p {
  color: #1f4f2b;
  line-height: 1.6;
  margin-bottom: 20px;
  font-size: 0.95rem;
}

.btn-view {
  padding: 12px 25px;
  border: none;
  border-radius: 20px;
  background-color: #1f4f2b;
  color: white;
  font-size: 0.95rem;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 700;
}

.btn-view:hover {
  background-color: #6b4f3a;
  transform: translateY(-3px) scale(1.05);
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
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

@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

@media (max-width: 768px) {
  .title {
    font-size: 2.2rem;
  }

  .section-title {
    font-size: 1.5rem;
  }

  .project-card,
  .cert-card,
  .social-card {
    width: 100%;
    max-width: 350px;
  }
}
</style>