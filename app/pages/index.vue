```vue
<script setup lang="ts">
import "../assets/style.css";
import Appheader from "../components/Appheader.vue";
import Appfooter from "../components/Appfooter.vue";
import { onMounted } from 'vue';

const { $anime } = useNuxtApp()
onMounted(() => {
  // Star Animation for Hero
  const hero = document.querySelector('.hero');
  for (let i = 0; i < 40; i++) {
    const star = document.createElement('div');
    star.className = 'star';
    star.style.left = `${Math.random() * 100}%`;
    star.style.top = `${Math.random() * 100}%`;
    star.style.animationDelay = `${Math.random() * 5}s`;
    hero?.appendChild(star);
  }

  // Hero Animation
  $anime({
    targets: '.hero-content h1',
    translateY: [-50, 0],
    opacity: [0, 1],
    easing: 'easeOutExpo',
    duration: 1500
  });

  $anime({
    targets: '.hero-content p, .hero-content .cta-button',
    translateY: [30, 0],
    opacity: [0, 1],
    delay: (el, i) => 800 + i * 200,
    easing: 'easeOutQuad'
  });

  // Intersection Observer for Scroll Animations
  const observerOptions = { threshold: 0.15 };
  
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const target = entry.target;
        
        if (target.classList.contains('presentation')) {
          $anime({
            targets: '.info-card',
            translateY: [60, 0],
            opacity: [0, 1],
            delay: (el, i) => i * 150,
            easing: 'easeOutExpo'
          });
        }
        
        if (target.classList.contains('rooms')) {
          $anime({
            targets: '.section-title',
            opacity: [0, 1],
            translateY: [30, 0],
            easing: 'easeOutQuad'
          });
          $anime({
            targets: '.room-card',
            scale: [0.9, 1],
            opacity: [0, 1],
            delay: (el, i) => 200 + i * 200,
            easing: 'easeOutBack(1.7)'
          });
        }

        if (target.classList.contains('contact-cta')) {
          $anime({
            targets: '.contact-cta > *',
            translateY: [40, 0],
            opacity: [0, 1],
            delay: (el, i) => i * 100,
            easing: 'easeOutSine'
          });
        }
        
        observer.unobserve(target);
      }
    });
  }, observerOptions);

  document.querySelectorAll('section').forEach(el => observer.observe(el));
});
</script>

<template>
  <div>
    <Appheader />

    <main class="hero">
      <div class="hero-content">
        <h1>Hotel Krone Munich</h1>
        <p>Boutique Elegance & Bavarian Hospitality</p>
        <button class="cta-button">Book Your Stay</button>
      </div>
    </main>

    <section class="presentation">
      <div class="container">
        <div class="info-card">
          <h3>Historic Charm</h3>
          <p>
            Experience the soul of Munich in our beautifully restored
            19th-century building.
          </p>
        </div>
        <div class="info-card">
          <h3>Modern Luxury</h3>
          <p>Enjoy contemporary comfort with traditional Bavarian warmth.</p>
        </div>
        <div class="info-card">
          <h3>Prime Location</h3>
          <p>Steps away from Theresienwiese and the heart of the city.</p>
        </div>
      </div>
    </section>

    <section class="rooms">
      <h2 class="section-title">Our Rooms</h2>
      <div class="room-grid">
        <div class="room-card">
          <div class="room-image"></div>
          <h3>Standard Room</h3>
          <p class="price">€120/night</p>
          <button class="cta-button">View Details</button>
        </div>
        <div class="room-card">
          <div class="room-image"></div>
          <h3>Deluxe Room</h3>
          <p class="price">€160/night</p>
          <button class="cta-button">View Details</button>
        </div>
        <div class="room-card">
          <div class="room-image"></div>
          <h3>Suite</h3>
          <p class="price">€220/night</p>
          <button class="cta-button">View Details</button>
        </div>
      </div>
    </section>

    <section class="contact-cta">
      <h2>Ready to Experience Krone?</h2>
      <p>Book your unforgettable stay in Munich today.</p>
      <button class="cta-button">Book Now</button>
    </section>
  </div>
  <Appfooter />
</template>

<style scoped>

.hero {
  height: 100vh;
  background: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)),
    url("https://images.unsplash.com/photo-1582719478250-c89ea26ee158?w=1200&h=800&fit=crop");
  background-size: cover;
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: white;
  overflow: hidden;
}

.hero-content h1 {
  font-size: 4rem;
  margin-bottom: 1rem;
  font-weight: 700;
}

.hero-content p {
  font-size: 1.5rem;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.cta-button {
  padding: 1rem 2rem;
  background: white;
  color: #333;
  border: none;
  border-radius: 4px;
  font-size: 1.1rem;
  cursor: pointer;
  transition: background 0.3s ease;
}

.cta-button:hover {
  background: #f0f0f0;
}

.presentation {
  padding: 4rem 2rem;
  background: #fcfbf7;
}

.presentation .container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.info-card {
  padding: 2rem;
  background: white;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.info-card h3 {
  color: #8b5e3c;
  margin-bottom: 1rem;
}

.rooms {
  padding: 4rem 2rem;
  background: #fcfbf7;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 3rem;
  color: #333;
}

.room-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.room-card {
  background: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.room-card:hover {
  transform: translateY(-5px);
}

.room-image {
  height: 200px;
  background: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.3)),
    url("https://images.unsplash.com/photo-1582719478250-c89ea26ee158?w=600&h=400&fit=crop");
  background-size: cover;
  background-position: center;
}

.room-card h3 {
  padding: 1.5rem;
  color: #333;
}

.price {
  padding: 0 1.5rem;
  color: #8b5e3c;
  font-weight: 600;
}

.room-card .cta-button {
  margin: 1.5rem;
  width: calc(100% - 3rem);
}

.contact-cta {
  padding: 4rem 2rem;
  background: #333;
  color: white;
  text-align: center;
}

.contact-cta h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.contact-cta p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
}

@media (max-width: 768px) {
  .hero-content h1 {
    font-size: 2.5rem;
  }

  .hero-content p {
    font-size: 1.2rem;
  }
}

</style>


    
