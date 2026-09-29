<template>
  <section class="showcase-section">
    <div class="section-header">
      <i class="fas fa-file-alt"></i>
      <h1 class="title">My Resume</h1>
      <i class="fas fa-file-alt"></i>
    </div>
    <p class="subtitle">View or download a copy of my CV below.</p>

    <div class="resume-page">
      <a href="/UPdate CV.pdf" download class="cv-download">
        <button class="btn-download">
          <i class="fas fa-download"></i> Download CV (PDF)
        </button>
      </a>

      <div class="project-card resume-preview">
        <embed src="/UPdate CV.pdf" type="application/pdf" width="100%" height="600px" />
      </div>

    </div>
  </section>
</template>

<script>
export default {
  name: 'ResumeView'
}
</script>

<style scoped>
.resume-page {
  max-width: 800px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px;
}
.cv-download { text-decoration: none; }
.resume-preview {
  width: 100%;
  padding: 12px;
}
.resume-preview embed { border-radius: 20px; }
</style>