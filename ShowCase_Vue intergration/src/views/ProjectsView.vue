<template>
  <section class="showcase-section">
    <div class="section-header">
      <i class="fas fa-star"></i>
      <h1 class="title">My Project Showcase</h1>
      <i class="fas fa-star"></i>
    </div>
    <p class="subtitle">Check out the amazing projects I've been working on!</p>

    <div class="projects-container">
      <div v-for="project in projects" :key="project.id" class="project-card">
        <div class="project-image-wrapper">
          <img :src="project.image" :alt="project.title" />
          <div class="project-badge">
            <i :class="project.badgeIcon"></i>
          </div>
        </div>
        <div class="project-content">
          <h2>{{ project.title }}</h2>
          <p>{{ project.description }}</p>
          <ul class="case-study">
            <li><strong>My role:</strong> {{ project.role }}</li>
            <li><strong>Tools:</strong> {{ project.tools }}</li>
          </ul>
          <div class="project-tags">
            <span v-for="tag in project.tags" :key="tag" class="tag">
              {{ tag }}
            </span>
          </div>
          <a :href="project.link" target="_blank" rel="noopener noreferrer" class="project-link">
            <button class="btn-view">
              <i class="fas fa-external-link-alt"></i> {{ project.buttonText }}
            </button>
          </a>
        </div>
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
          title: 'CampusSwap SA',
          description:
            'A student marketplace for buying and selling academic items such as textbooks. I built the Academic Marketplace page as part of a team, working on the Vue frontend while the backend was built separately.',
          role: 'Frontend developer (Academic Marketplace page)',
          tools: 'VS Code, Vue.js, JavaScript, HTML, CSS',
          image: '/github.png',
          link: 'https://campusswap-fontend.onrender.com',
          buttonText: 'View Live Site',
          badgeIcon: 'fas fa-graduation-cap',
          tags: ['Vue.js', 'Frontend', 'Team Project']
        },
        {
          id: 2,
          title: 'HRFlow',
          description:
            'A payroll and HR web app for a company called ModernTech, with a secure sign-in and pages for payroll and employee performance. It keeps employee records, payslips and attendance in one place.',
          role: 'Web developer',
          tools: 'VS Code, HTML, CSS, JavaScript',
          image: '/github.png',
          link: 'https://hrflow-xg3y.onrender.com',
          buttonText: 'View Live Site',
          badgeIcon: 'fas fa-users',
          tags: ['Full Stack', 'Payroll', 'HR']
        },
        {
          id: 3,
          title: 'YouthConnect',
          description:
            'A platform connecting young people with internships, jobs, training programmes and freelance opportunities, with profile creation, opportunity browsing and proposal submission.',
          role: 'Web developer',
          tools: 'VS Code, HTML, CSS, JavaScript',
          image: '/github.png',
          link: 'https://zaarah-okkers.github.io/YouthConnect/',
          buttonText: 'View Live Site',
          badgeIcon: 'fas fa-briefcase',
          tags: ['Frontend', 'Career Platform']
        },
        {
          id: 4,
          title: 'Python Mini Toolkit',
          description:
            'A mini toolkit that solves common beginner coding tasks and exercises in one place. I designed and wrote it myself to practise Python fundamentals.',
          role: 'Solo developer',
          tools: 'VS Code, Python, Git, GitHub',
          image: '/github.png',
          link: 'https://github.com/Zaarah-Okkers',
          buttonText: 'View Project',
          badgeIcon: 'fas fa-code',
          tags: ['Python', 'Backend', 'Toolkit']
        },
        {
          id: 5,
          title: 'Novel Nest',
          description:
            'A responsive book marketplace website. I designed the branding and layout and built every page to work on desktop and mobile.',
          role: 'Solo designer and developer',
          tools: 'VS Code, HTML, CSS',
          image: '/Novel Nest (1).jpg',
          link: '/Novel%20Nest/Index.html',
          buttonText: 'View Project',
          badgeIcon: 'fas fa-book',
          tags: ['HTML', 'CSS', 'Design']
        },
        {
          id: 6,
          title: 'HTML & CSS Showcase',
          description:
            'A modern showcase website that demonstrates my front-end styling skills, later rebuilt with Vue.js and Vue Router into this portfolio.',
          role: 'Solo developer',
          tools: 'VS Code, HTML, CSS, JavaScript, Vue.js, SweetAlert',
          image: '/Screenshot 2026-05-29 112635.png',
          link: 'https://github.com/Zaarah-Okkers',
          buttonText: 'View Project',
          badgeIcon: 'fas fa-palette',
          tags: ['HTML', 'CSS', 'Frontend']
        }
      ]
    }
  }
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

.showcase-section {
  min-height: 100vh;
  padding: 100px 20px;
  background: linear-gradient(135deg, var(--hello-kitty-cream) 0%, var(--hello-kitty-light-pink) 100%);
  background-attachment: fixed;
  text-align: center;
  position: relative;
}

.showcase-section::before {
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

.section-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  margin-bottom: 15px;
  position: relative;
  z-index: 1;
}

.section-header i {
  font-size: 2rem;
  color: var(--hello-kitty-red);
  animation: bounce 2s ease-in-out infinite;
}

.title {
  font-size: 3.5rem;
  color: var(--hello-kitty-red);
  margin-bottom: 0;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
  font-weight: 900;
}

.subtitle {
  font-size: 1.1rem;
  color: var(--hello-kitty-red);
  margin-bottom: 50px;
  position: relative;
  z-index: 1;
  font-weight: 600;
}

.projects-container {
  display: flex;
  justify-content: center;
  gap: 35px;
  flex-wrap: wrap;
  position: relative;
  z-index: 1;
}

.project-card {
  width: 320px;
  background: rgba(255, 255, 255, 0.12);
  backdrop-filter: blur(8px);
  border-radius: 25px;
  overflow: hidden;
  padding-bottom: 25px;
  box-shadow: 0 8px 20px rgba(255, 20, 147, 0.12);
  transition: all 0.4s ease;
  animation: fadeUp 1s ease;
  border: 2px solid rgba(255, 255, 255, 0.25);
  display: flex;
  flex-direction: column;
}

.project-card:hover {
  transform: translateY(-12px);
  box-shadow: 0 12px 28px rgba(255, 20, 147, 0.2);
  background: rgba(255, 255, 255, 0.18);
}

.project-image-wrapper {
  position: relative;
  overflow: hidden;
  height: 220px;
}

.project-card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.project-card:hover img {
  transform: scale(1.08);
}

.project-badge {
  position: absolute;
  top: 15px;
  right: 15px;
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, var(--hello-kitty-red) 0%, #ff69b4 100%);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 1.5rem;
  box-shadow: 0 4px 12px rgba(255, 20, 147, 0.25);
  animation: spin 3s linear infinite;
}

.project-content {
  padding: 20px;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.project-card h2 {
  margin: 0 0 10px;
  color: white;
  font-size: 1.3rem;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.15);
}

.project-card p {
  line-height: 1.6;
  color: rgba(255, 255, 255, 0.95);
  margin-bottom: 15px;
  font-size: 0.95rem;
  flex-grow: 1;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 15px;
}

.tag {
  background: rgba(255, 255, 255, 0.2);
  color: white;
  padding: 5px 12px;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.project-link {
  text-decoration: none;
  margin-top: auto;
}

.btn-view {
  width: 100%;
  padding: 12px 20px;
  border: 2px solid white;
  border-radius: 20px;
  background: linear-gradient(135deg, var(--hello-kitty-red) 0%, #ff69b4 100%);
  color: white;
  font-size: 0.95rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.btn-view:hover {
  background: linear-gradient(135deg, #ff69b4 0%, var(--hello-kitty-red) 100%);
  transform: translateY(-3px);
  box-shadow: 0 6px 16px rgba(255, 20, 147, 0.25);
}

.btn-view i {
  font-size: 1rem;
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

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

@media (max-width: 768px) {
  .title {
    font-size: 2.5rem;
  }

  .subtitle {
    font-size: 0.95rem;
  }

  .project-card {
    width: 100%;
    max-width: 350px;
  }

  .section-header {
    gap: 10px;
  }

  .section-header i {
    font-size: 1.5rem;
  }
}
</style>