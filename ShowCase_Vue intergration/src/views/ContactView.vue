<template>
  <section class="contact-section">
    <h2 class="contact-title">Get In Touch</h2>
    <form class="contact-form" @submit.prevent="submitForm">
      <label for="name">Name</label>
      <input 
        id="name"
        v-model="formData.name" 
        type="text" 
        placeholder="Your Name" 
        required
      />

      <label for="email">Email</label>
      <input 
        id="email"
        v-model="formData.email" 
        type="email" 
        placeholder="Your Email" 
        required
      />

      <label for="message">Message</label>
      <textarea 
        id="message"
        v-model="formData.message" 
        placeholder="Your Message" 
        rows="5"
        required
      ></textarea>

      <button type="submit" class="btn-submit">Send Message</button>
    </form>
  </section>
</template>

<script>
export default {
  name: 'ContactView',
  data() {
    return {
      formData: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      fetch('https://formspree.io/f/xjgznpwl', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(this.formData)
      })
        .then(response => {
          if (response.ok) {
            alert('Thank you for your message! I will get back to you soon.')
            this.formData = { name: '', email: '', message: '' }
          } else {
            alert('Error sending message. Please try again.')
          }
        })
        .catch(error => {
          console.error('Error:', error)
          alert('Error sending message. Please try again.')
        })
    }
  }
}
</script>

<style scoped>
.contact-section {
  min-height: 100vh;
  padding: 100px 20px;
  background: linear-gradient(135deg, #f5ebdd, #709a5f);
}

.contact-title {
  text-align: center;
  font-size: 3rem;
  color: #1f4f2b;
  margin-bottom: 40px;
}

.contact-form {
  max-width: 700px;
  margin: auto;
  padding: 40px;
  border-radius: 25px;
  background: #709a5f;
  backdrop-filter: blur(10px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.25);
}

.contact-form label {
  display: block;
  margin-bottom: 8px;
  color: white;
  font-weight: bold;
}

.contact-form input,
.contact-form textarea {
  width: 100%;
  padding: 14px;
  margin-bottom: 20px;
  border: 2px solid #1f4f2b;
  border-radius: 12px;
  background: #f5ebdd;
  color: #1f4f2b;
  font-size: 1rem;
  font-family: Arial, sans-serif;
}

.contact-form input:focus,
.contact-form textarea:focus {
  border-color: #d4a373;
  outline: none;
}

.btn-submit {
  width: 100%;
  padding: 14px 30px;
  border: none;
  border-radius: 30px;
  background-color: #1f4f2b;
  color: white;
  font-size: 1rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-submit:hover {
  background-color: #6b4f3a;
  transform: translateY(-5px) scale(1.05);
}

@media (max-width: 768px) {
  .contact-title {
    font-size: 2.2rem;
  }

  .contact-form {
    padding: 20px;
  }
}
</style>