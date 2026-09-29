<template>
  <section class="showcase-section">
    <div class="section-header">
      <i class="fas fa-rocket"></i>
      <h1 class="title">Skills & Tech Stack</h1>
      <i class="fas fa-rocket"></i>
    </div>
    <p class="subtitle">The languages, frameworks and tools I build with.</p>

    <div class="skills-page">
      <div v-for="group in skillGroups" :key="group.name" class="project-card skills-card">
        <h2><i :class="group.icon"></i> {{ group.name }}</h2>
        <div class="skills-grid">
          <div v-for="skill in group.skills" :key="skill" class="skill-tag">{{ skill }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SkillsView',
  data() {
    return {
      skillGroups: [
        {
          name: 'Frontend',
          icon: 'fas fa-palette',
          skills: ['HTML', 'CSS', 'JavaScript', 'Vue.js', 'Vue Router', 'SweetAlert']
        },
        {
          name: 'Backend & Languages',
          icon: 'fas fa-server',
          skills: ['Python']
        },
        {
          name: 'Tools',
          icon: 'fas fa-toolbox',
          skills: ['VS Code', 'Git', 'GitHub']
        }
      ]
    }
  }
}
</script>

<style scoped>
.skills-page {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 30px;
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 20px;
}
.skills-card h2 {
  margin-bottom: 16px;
  display: flex;
  align-items: center;
  gap: 10px;
}
</style>