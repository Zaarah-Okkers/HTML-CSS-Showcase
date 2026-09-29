<template>
  <section class="showcase-section">
    <div class="section-header">
      <i class="fas fa-quote-right"></i>
      <h1 class="title">Testimonials</h1>
      <i class="fas fa-quote-right"></i>
    </div>
    <p class="subtitle">What people I've worked with have to say.</p>

    <div class="testimonials-page">
      <div v-for="item in testimonials" :key="item.name" class="project-card testimonial-card">
        <i class="fas fa-quote-left quote-icon"></i>
        <p class="quote">{{ item.quote }}</p>
        <p class="quote-author">— {{ item.name }}, {{ item.role }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TestimonialsView',
  data() {
    return {
      testimonials: [
        { quote: '[Working with Zaarah you can expect your expectations to be exceeded]', name: '[Ihtishaam Johnson]', role: '[Team Leader]' },
        { quote: '[Working with Zaarah is not just working. She makes things fun and enjoyable and never disappoints.]', name: '[Ishmaiel grey]', role: '[Frontend Dev]' }
      ]
    }
  }
}
</script>

<style scoped>
.testimonials-page {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 20px;
}
.testimonial-card { text-align: center; padding: 30px; }
.quote-icon { font-size: 1.8rem; color: var(--kt-hot, #f0508f); margin-bottom: 10px; }
.quote { font-style: italic; margin-bottom: 14px; }
.quote-author { font-weight: bold; color: var(--kt-hot, #f0508f); }
</style>