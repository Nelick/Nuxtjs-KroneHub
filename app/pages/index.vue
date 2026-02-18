<script setup lang="ts">
import "../assets/style.css";
import Appheader from "../components/Appheader.vue";
import Appfooter from "../components/Appfooter.vue";
</script>

<template>
  <div>
    <Appheader />

    <main class="hero">
      <div class="hero-content">
        <h1 class="fade-in">Hotel Krone Munich</h1>
        <p class="slide-up">Boutique Elegance & Bavarian Hospitality</p>
        <button class="cta-button">Book Your Stay</button>
      </div>
    </main>

    <section class="presentation">
      <div class="container">
        <div class="info-card reveal">
          <h3>Historic Charm</h3>
          <p>
            Experience the soul of Munich in our beautifully restored
            19th-century building.
          </p>
        </div>
        <div class="info-card reveal delay-1">
          <h3>Modern Luxury</h3>
          <p>Enjoy contemporary comfort with traditional Bavarian warmth.</p>
        </div>
        <div class="info-card reveal delay-2">
          <h3>Prime Location</h3>
          <p>Steps away from Theresienwiese and the heart of the city.</p>
        </div>
      </div>
    </section>

    <section class="rooms">
      <h2 class="section-title reveal">Our Rooms</h2>
      <div class="room-grid">
        <div class="room-card reveal">
          <div class="room-image"></div>
          <h3>Standard Room</h3>
          <p class="price">€120/night</p>
          <button class="cta-button">View Details</button>
        </div>
        <div class="room-card reveal delay-1">
          <div class="room-image"></div>
          <h3>Deluxe Room</h3>
          <p class="price">€160/night</p>
          <button class="cta-button">View Details</button>
        </div>
        <div class="room-card reveal delay-2">
          <div class="room-image"></div>
          <h3>Suite</h3>
          <p class="price">€220/night</p>
          <button class="cta-button">View Details</button>
        </div>
      </div>
    </section>

    <section class="contact-cta reveal">
      <h2>Ready to Experience Krone?</h2>
      <p>Book your unforgettable stay in Munich today.</p>
      <button class="cta-button">Book Now</button>
    </section>
  </div>
  <Appfooter />
</template>
<style>
/* Base Styles */
.hero {
  height: 100vh;
  background:
    linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)),
    url("https://images.unsplash.com/photo-1582719478250-c89ea26ee158?w=1200&h=800&fit=crop");
  background-size: cover;
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: white;
}

.hero-content h1 {
  font-size: 4rem;
  margin-bottom: 1rem;
  font-family: "Playfair Display", serif;
}

.hero-content p {
  font-size: 1.5rem;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.cta-button {
  background: #b59a5d;
  color: white;
  border: none;
  padding: 1rem 2rem;
  font-size: 1.2rem;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s;
}

.cta-button:hover {
  background: #a38a50;
}

/* Presentation Section */
.presentation {
  padding: 4rem 2rem;
  background: #fdfcf8;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.info-card {
  background: white;
  padding: 2rem;
  border-radius: 10px;
  margin: 1rem 0;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.6s ease-out;
}

.info-card.reveal {
  opacity: 1;
  transform: translateY(0);
}

.info-card h3 {
  color: #2c3e50;
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

/* Rooms Section */
.rooms {
  padding: 4rem 2rem;
  background: #f4f1ea;
}

.section-title {
  text-align: center;
  font-size: 2.5rem;
  margin-bottom: 3rem;
  color: #2c3e50;
  font-family: "Playfair Display", serif;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.6s ease-out;
}

.section-title.reveal {
  opacity: 1;
  transform: translateY(0);
}

.room-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.room-card {
  background: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.6s ease-out;
}

.room-card.reveal {
  opacity: 1;
  transform: translateY(0);
}

.room-image {
  height: 200px;
  background: #ccc;
  background-size: cover;
  background-position: center;
}

.room-card h3 {
  padding: 1rem 1.5rem;
  color: #2c3e50;
}

.room-card .price {
  padding: 0 1.5rem;
  color: #b59a5d;
  font-weight: bold;
  margin-bottom: 1rem;
}

/* Contact CTA */
.contact-cta {
  padding: 4rem 2rem;
  background: #2c3e50;
  color: white;
  text-align: center;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.6s ease-out;
}

.contact-cta.reveal {
  opacity: 1;
  transform: translateY(0);
}

.contact-cta h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
  font-family: "Playfair Display", serif;
}

.contact-cta p {
  font-size: 1.2rem;
  margin-bottom: 2rem;
}

/* Animations */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.fade-in {
  animation: fadeIn 1s ease-out forwards;
}

.slide-up {
  animation: slideUp 1s ease-out forwards;
}

.delay-1 {
  animation-delay: 0.2s;
}

.delay-2 {
  animation-delay: 0.4s;
}

/* Responsive */
@media (max-width: 768px) {
  .hero-content h1 {
    font-size: 2.5rem;
  }

  .room-grid {
    grid-template-columns: 1fr;
  }
}
</style>
