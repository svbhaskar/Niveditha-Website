<template>
  <div id="app">
    <!-- Hero Section -->
    <section class="hero">
      <img :src="heroImg" alt="Hero" class="hero-img" />
      <div class="hero-content">
        <div class="logo-container">
          <img :src="logoImg" alt="College Logo" class="logo" />
        </div>
        <div class="title-container">
          <h1>{{ college.name }}</h1>
          <p>{{ college.tagline }}</p>
        </div>
      </div>
    </section>

    <div class="container">
      <!-- About Section -->
      <section class="content-section">
        <div class="section-content">
          <h2>About College</h2>
          <p>{{ college.description }}</p>
          <p>{{ college.staffNote }}</p>
        </div>
      </section>

      <!-- Location & Management Section -->
      <section class="content-section alternate">
        <div class="section-content">
          <h2>Location & Management</h2>
          <div class="info-grid">
            <div class="info-block">
              <h3>📍 Location</h3>
              <p>{{ location }}</p>
            </div>
            <div class="info-block">
              <h3>🏢 Management</h3>
              <p>{{ management }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- Library Section -->
      <section class="content-section">
        <div class="section-content">
          <h2>Library</h2>
          <p>{{ libraryInfo }}</p>
        </div>
      </section>

      <!-- Activities Section -->
      <section class="content-section alternate">
        <div class="section-content">
          <h2>Extra Curricular Activities</h2>
          <p>{{ activities }}</p>
        </div>
      </section>

      <!-- Photo Gallery -->
      <section class="content-section gallery-section">
        <div class="section-content">
          <h2>College Photos</h2>
          <div class="photo-grid">
            <img :src="college1" alt="College Photo 1" class="photo" />
            <img :src="college2" alt="College Photo 2" class="photo" />
            <img :src="college3" alt="College Photo 3" class="photo" />
          </div>
        </div>
      </section>

      <!-- Contact Information -->
      <section class="content-section contact-section">
        <div class="section-content">
          <h2>Contact Information</h2>
          <div class="contact-grid">
            <div class="contact-item">
              <span class="contact-icon">📞</span>
              <div>
                <strong>Phone</strong>
                <p>{{ contact.phone }}</p>
              </div>
            </div>
            <div class="contact-item">
              <span class="contact-icon">📱</span>
              <div>
                <strong>Mobile</strong>
                <p>{{ contact.mobile1 }} | {{ contact.mobile2 }}</p>
              </div>
            </div>
            <div class="contact-item full-width">
              <span class="contact-icon">📍</span>
              <div>
                <strong>Address</strong>
                <p>{{ contact.address }}</p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <footer class="footer">
        <p>© {{ new Date().getFullYear() }} {{ college.name }}</p>
      </footer>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import college1 from './assets/front.jpeg'
import college2 from './assets/lab.jpeg'
import college3 from './assets/office.jpeg'
import heroImg from './assets/hero.png'
import logoImg from './assets/logo.jpeg'

const college = ref({
  name: 'Niveditha College of Pharmacy',
  tagline: 'Excellence in Pharmaceutical Education',
  description: 'The Niveditha College of Pharmacy was established by highly qualified and experienced Pharmacy Professionals under the auspices of Niveditha Education Trust, Chintamani in the year 1992, with a major goal of imparting Quality Education and uplifting the Pharmacy Profession. The College possessing a sprawling building of it\'s own with well equipped laboratories and class rooms. It is a matter of pride mentioning that the college achieved best results in the state from first year onwards and secured two state ranks 6th & 10th in 1997 Exams, 3rd and 7th in 1999 exams, 5th in 2000 exams and 8th and 9th in 2002 exams, 8th rank in 2018. This unique credit goes to the Principal and band of well merited and devoted lectures.',
  staffNote: 'The college is supported by well qualified and experienced staff.'
})

const location = ref('Chintamani is a taluk headquarters having a population around 1 lakh and is located 70 Kms, away from Bangalore City on Bangalore Cudapa Road.')

const management = ref('Niveditha Education Trust, Chintamani')

const libraryInfo = ref('The College provides a spacious library containing many standard books for the ready reference to the students, in addition to it the library receives a wide range of Journals, Magazines and daily Newspapers with special reference to Pharmacy Course. A few journals have been received from Foreign Countries also.')

const activities = ref('Regular Sports, literacy and cultural competitions are conducted to improve the talent of the students and to enhance their self-confidence. The sports meet is held every year and prizes to the winners in all the competitions are awarded in the valedictory function of the college. Pharmacy week once in a year will be celebrated with exhibitions. Medical check-up for the public and seminars, Guest lecturers will be arranged timing the week.')

const contact = ref({
  phone: '0851-451405',
  mobile1: '944825026',
  mobile2: '7019156189',
  address: 'Opp. old LIC Office, Gandhinagar Extn, Bangalore Road, Chintamani - 563 125, Chikballapur Dist, Karnataka'
})

const heroUrl = heroImg
</script>

<style scoped>
body {
  margin: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: #333;
  background-color: #f8f9fa;
}

#app {
  min-height: 100vh;
}

.hero {
  position: relative;
  color: white;
  padding: 50px 40px;
  text-align: center;
  overflow: hidden;
  background: linear-gradient(135deg, #1e293b 0%, #334155 100%);
  width: 100%;
  display: flex;
  align-items: center;
}

.hero-img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: 1;
  opacity: 0.3;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0,0,0,0.4);
  z-index: 2;
}

.hero-content {
  position: relative;
  z-index: 3;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 30px;
  min-height: 300px;
}

.logo-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 10px;
}

.logo {
  width: 140px;
  height: 140px;
  object-fit: contain;
  background: rgba(255,255,255,0.95);
  padding: 15px;
  border-radius: 16px;
  box-shadow: 0 8px 24px rgba(0,0,0,0.2);
  flex-shrink: 0;
}

.title-container {
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.hero h1 {
  font-size: 3rem;
  margin: 0;
  font-weight: 800;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
  line-height: 1.1;
  color: white;
}

.hero p {
  font-size: 1.3rem;
  opacity: 0.95;
  font-weight: 500;
  text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
  margin: 0;
  text-align: center;
}

.logo {
  position: absolute;
  top: 30px;
  left: 40px;
  width: 120px;
  height: 120px;
  object-fit: contain;
  z-index: 3;
  background: rgba(255,255,255,0.95);
  padding: 12px;
  border-radius: 16px;
  box-shadow: 0 8px 24px rgba(0,0,0,0.2);
}

.container {
  width: 100%;
  padding: 0;
}

.content-section {
  padding: 80px 40px;
  background: #ffffff;
  width: 100%;
}

.content-section.alternate {
  background: #f1f5f9;
}

.content-section.contact-section {
  background: #0f172a;
  color: white;
}

.section-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.content-section h2 {
  color: #1e293b;
  font-size: 2.8rem;
  font-weight: 700;
  margin-bottom: 40px;
  text-align: center;
  position: relative;
}

.content-section.alternate h2 {
  color: #1e293b;
}

.content-section.contact-section h2 {
  color: #ffffff;
}

.content-section h2::after {
  content: '';
  display: block;
  width: 80px;
  height: 5px;
  background: linear-gradient(90deg, #3b82f6, #6366f1);
  margin: 20px auto 0;
  border-radius: 3px;
}

.content-section.alternate h2::after {
  background: linear-gradient(90deg, #10b981, #3b82f6);
}

.content-section.contact-section h2::after {
  background: linear-gradient(90deg, #ef4444, #f97316);
}

.content-section p {
  font-size: 1.2rem;
  line-height: 1.8;
  color: #475569;
  margin-bottom: 25px;
  text-align: justify;
}

.content-section.alternate p {
  color: #334155;
}

.content-section.contact-section p {
  color: #cbd5e1;
}

.info-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 50px;
  margin-top: 50px;
}

.info-block {
  background: #ffffff;
  padding: 40px;
  border-radius: 16px;
  box-shadow: 0 8px 32px rgba(0,0,0,0.1);
  border-left: 5px solid #3b82f6;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid #e2e8f0;
}

.info-block:hover {
  transform: translateY(-8px);
  box-shadow: 0 16px 48px rgba(0,0,0,0.15);
}

.info-block h3 {
  color: #1e293b;
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 10px;
}

.info-block p {
  margin: 0;
  color: #475569;
  line-height: 1.7;
  font-size: 1.1rem;
}

.gallery-section {
  text-align: center;
  padding: 100px 40px;
  background: #ffffff;
}

.photo-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 40px;
  margin-top: 50px;
  max-width: 1400px;
  margin-left: auto;
  margin-right: auto;
}

.photo {
  width: 100%;
  height: 280px;
  object-fit: cover;
  border-radius: 16px;
  box-shadow: 0 12px 40px rgba(0,0,0,0.15);
  transition: transform 0.4s ease, box-shadow 0.4s ease;
  border: 4px solid #ffffff;
}

.photo:hover {
  transform: scale(1.05) rotate(2deg);
  box-shadow: 0 20px 60px rgba(0,0,0,0.25);
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 40px;
  margin-top: 50px;
}

.contact-item {
  display: flex;
  align-items: flex-start;
  gap: 25px;
  background: rgba(255,255,255,0.08);
  padding: 35px;
  border-radius: 16px;
  border: 2px solid rgba(255,255,255,0.15);
  backdrop-filter: blur(12px);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.contact-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 32px rgba(0,0,0,0.2);
}

.contact-item.full-width {
  grid-column: 1 / -1;
  background: rgba(255,255,255,0.12);
  border: 2px solid rgba(255,255,255,0.2);
}

.contact-icon {
  font-size: 2.5rem;
  color: #3b82f6;
  margin-top: 8px;
  flex-shrink: 0;
}

.contact-item strong {
  display: block;
  font-size: 1.4rem;
  margin-bottom: 12px;
  color: #ffffff;
  font-weight: 700;
}

.contact-item p {
  margin: 0;
  color: #cbd5e1;
  line-height: 1.6;
  font-size: 1.1rem;
}

.footer {
  text-align: center;
  padding: 60px 40px;
  background: #1e293b;
  color: #ffffff;
  font-size: 1.1rem;
  border-top: 3px solid #3b82f6;
  width: 100%;
}

ul {
  list-style: none;
  padding: 0;
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero {
    padding: 60px 20px;
    min-height: 450px;
  }

  .hero-content {
    padding: 30px 15px 0 15px;
    gap: 25px;
  }

  .logo-container {
    margin-bottom: 5px;
  }

  .logo {
    width: 125px;
    height: 125px;
    padding: 12px;
  }

  .title-container {
    gap: 12px;
  }

  .hero h1 {
    font-size: 2.2rem;
    text-align: center;
  }

  .hero p {
    font-size: 1.1rem;
    text-align: center;
  }

  .hero p {
    font-size: 1.1rem;
  }

  .content-section {
    padding: 60px 20px;
  }

  .content-section h2 {
    font-size: 2.2rem;
  }

  .section-content {
    padding: 0 15px;
  }

  .info-grid {
    grid-template-columns: 1fr;
    gap: 30px;
  }

  .photo-grid {
    grid-template-columns: 1fr;
    gap: 25px;
  }

  .contact-grid {
    grid-template-columns: 1fr;
  }

  .contact-item {
    padding: 25px;
    flex-direction: column;
    text-align: center;
    gap: 15px;
  }

  .contact-icon {
    margin-top: 0;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 60px 15px;
    min-height: 450px;
  }

  .hero-content {
    padding: 30px 10px 0 10px;
    gap: 25px;
  }

  .logo-container {
    margin-bottom: 5px;
  }

  .logo {
    width: 110px;
    height: 110px;
    padding: 10px;
  }

  .title-container {
    gap: 10px;
  }

  .hero h1 {
    font-size: 1.8rem;
    text-align: center;
    line-height: 1.2;
  }

  .hero p {
    font-size: 0.9rem;
    text-align: center;
  }

  .content-section h2 {
    font-size: 1.8rem;
  }

  .content-section p {
    font-size: 1rem;
  }

  .info-block {
    padding: 25px;
  }

  .info-block h3 {
    font-size: 1.2rem;
  }

  .contact-item strong {
    font-size: 1.2rem;
  }
}

li {
  padding: 8px 0;
  border-bottom: 1px solid #eee;
}

li:last-child {
  border-bottom: none;
}

@media (max-width: 768px) {
  .hero h1 {
    font-size: 2rem;
  }
  .section {
    padding: 20px;
  }
  .main-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }
  .photo-grid {
    grid-template-columns: 1fr;
  }
  .contact-grid {
    grid-template-columns: 1fr;
  }
  .contact-item.full-width {
    grid-column: 1;
  }
  .logo {
    width: 80px;
    height: 80px;
  }
}
</style>
