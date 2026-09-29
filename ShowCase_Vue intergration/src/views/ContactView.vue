<template>
  <section class="contact-section">
    <div class="contact-wrapper">
      <div class="section-header">
        <i class="fas fa-envelope"></i>
        <h1 class="contact-title">Get in Touch</h1>
        <i class="fas fa-envelope"></i>
      </div>
      <p class="contact-subtitle">I'd love to hear from you! Send me a message and I'll get back to you as soon as possible.</p>

      <ul class="contact-details">
        <li><i class="fas fa-envelope"></i> <a href="mailto:zaarahokkers@gmail.com">zaarahokkers@gmail.com</a></li>
        <li><i class="fas fa-phone"></i> <a href="tel:+27692461456">069 246 1456</a></li>
        <li><i class="fab fa-linkedin"></i> <a href="https://www.linkedin.com/in/zaarah-okkers-3688b1377" target="_blank" rel="noopener noreferrer">LinkedIn</a></li>
        <li><i class="fab fa-github"></i> <a href="https://github.com/Zaarah-Okkers" target="_blank" rel="noopener noreferrer">GitHub</a></li>
      </ul>

      <form @submit.prevent="submitForm" class="contact-form">
        <div class="form-group">
          <label for="name"><i class="fas fa-user"></i> Name</label>
          <input type="text" id="name" v-model="formData.name" placeholder="Your Name" class="form-input" required />
        </div>

        <div class="form-group">
          <label for="email"><i class="fas fa-envelope"></i> Email</label>
          <input type="email" id="email" v-model="formData.email" placeholder="your@email.com" class="form-input" required />
        </div>

        <div class="form-group">
          <label for="message"><i class="fas fa-comment"></i> Message</label>
          <textarea id="message" v-model="formData.message" placeholder="Write your message here... Tell me about your project ideas!" class="form-input" rows="6" required></textarea>
        </div>

        <div class="button-container">
          <button type="submit" class="btn-submit">
            <i class="fas fa-paper-plane"></i> Send Message
          </button>
        </div>

        <p class="form-note">
          <i class="fas fa-heart"></i> Thank you for reaching out!
        </p>
      </form>
    </div>
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
      },
      submitStatus: null
    }
  },
  methods: {
    submitForm() {
      // Send form data to Formspree
      fetch('https://formspree.io/f/xjgznpwl', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(this.formData)
      })
        .then(response => {
          if (response.ok) {
            this.submitStatus = 'success'
            this.formData = { name: '', email: '', message: '' }
            setTimeout(() => {
              this.submitStatus = null
            }, 5000)
          } else {
            this.submitStatus = 'error'
          }
        })
        .catch(error => {
          console.error('Error:', error)
          this.submitStatus = 'error'
        })
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

.contact-section {
  min-height: 100vh;
  padding: 100px 20px;
  background: linear-gradient(135deg, var(--hello-kitty-cream) 0%, var(--hello-kitty-light-pink) 100%);
  background-attachment: fixed;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.contact-section::before {
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

.contact-wrapper {
  max-width: 700px;
  width: 100%;
  position: relative;
  z-index: 2;
}

.section-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  margin-bottom: 20px;
}

.section-header i {
  font-size: 2.5rem;
  color: var(--hello-kitty-red);
  animation: bounce 2s ease-in-out infinite;
}

.contact-title {
  text-align: center;
  font-size: 3rem;
  color: var(--hello-kitty-red);
  margin-bottom: 0;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
  font-weight: 900;
}

.contact-subtitle {
  text-align: center;
  font-size: 1.05rem;
  color: var(--hello-kitty-red);
  margin-bottom: 40px;
  font-weight: 600;
}

.contact-form {
  padding: 50px;
  border-radius: 30px;
  background: linear-gradient(135deg, var(--hello-kitty-pink) 0%, #ff69b4 100%);
  box-shadow: 0 10px 30px rgba(255, 20, 147, 0.2);
  border: 2px solid rgba(255, 255, 255, 0.25);
  animation: slideUp 1s ease;
  position: relative;
}

.contact-form::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: 
    repeating-linear-gradient(45deg, transparent, transparent 20px, rgba(255, 255, 255, 0.02) 20px, rgba(255, 255, 255, 0.02) 40px);
  border-radius: 30px;
  pointer-events: none;
}

.form-group {
  margin-bottom: 25px;
  position: relative;
  z-index: 1;
}

.form-group label {
  display: block;
  margin-bottom: 10px;
  color: white;
  font-weight: 700;
  font-size: 1.05rem;
  display: flex;
  align-items: center;
  gap: 8px;
}

.form-group label i {
  font-size: 1.2rem;
  animation: bounce 1.5s ease-in-out infinite;
}

.form-input {
  width: 100%;
  padding: 15px;
  border: 3px solid white;
  border-radius: 15px;
  background: rgba(255, 255, 255, 0.95);
  color: var(--hello-kitty-red);
  font-size: 1rem;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  transition: all 0.3s ease;
}

.form-input::placeholder {
  color: rgba(255, 20, 147, 0.5);
  font-weight: 500;
}

.form-input:focus {
  border-color: var(--hello-kitty-cream);
  outline: none;
  box-shadow: 0 0 8px rgba(255, 255, 255, 0.3);
  background: white;
  transform: translateY(-2px);
}

.form-input:hover {
  border-color: var(--hello-kitty-cream);
}

textarea.form-input {
  resize: vertical;
  min-height: 150px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.button-container {
  display: flex;
  justify-content: center;
  margin: 30px 0 20px;
  position: relative;
  z-index: 1;
}

.btn-submit {
  padding: 16px 45px;
  border: 3px solid white;
  border-radius: 30px;
  background: rgba(255, 255, 255, 0.2);
  color: white;
  font-size: 1.1rem;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.15);
}

.btn-submit:hover {
  background: white;
  color: var(--hello-kitty-red);
  transform: translateY(-5px);
  box-shadow: 0 10px 24px rgba(255, 255, 255, 0.3);
}

.btn-submit:active {
  transform: translateY(-2px);
}

.btn-submit i {
  font-size: 1.2rem;
  animation: slideRight 0.6s ease-in-out infinite;
}

.form-note {
  text-align: center;
  color: white;
  font-weight: 600;
  font-size: 0.95rem;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  position: relative;
  z-index: 1;
}

.form-note i {
  color: #ffff00;
  animation: bounce 1.5s ease-in-out infinite;
}

/* ANIMATIONS */
@keyframes slideUp {
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

@keyframes slideRight {
  0%, 100% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(8px);
  }
}

@media (max-width: 768px) {
  .contact-form {
    padding: 30px 20px;
    border-radius: 20px;
  }

  .contact-title {
    font-size: 2.2rem;
  }

  .contact-subtitle {
    font-size: 0.95rem;
  }

  .form-group label {
    font-size: 0.95rem;
  }

  .form-input {
    padding: 12px;
    border-radius: 10px;
  }

  .btn-submit {
    padding: 12px 35px;
    font-size: 0.95rem;
  }

  .section-header i {
    font-size: 1.8rem;
  }
}
</style>