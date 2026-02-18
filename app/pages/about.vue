```vue
<script setup lang="ts">
import "@/assets/style.css";
import Appheader from "../components/Appheader.vue";
import Appfooter from "../components/Appfooter.vue";
</script>

<template>
  <div class="container">
    <Appheader />
    <main class="about-content">
      <section class="hero-section">
        <h1>Boutique Hotel Krone</h1>
        <p class="tagline">Timeless Elegance in the Heart of Munich</p>
      </section>

      <section class="description">
        <div class="brand-story">
          <h2>Our Story</h2>
          <p>
            Nestled directly by the legendary Theresienwiese, Boutique Hotel
            Krone is more than just a place to stay—it's a sanctuary of Bavarian
            hospitality. Since our inception, we have combined the historic
            charm of Munich with modern, boutique design to create an atmosphere
            of sophisticated comfort.
          </p>
        </div>

        <div class="amenities-grid">
          <div class="amenity-card">
            <h3>Prime Location</h3>
            <p>
              Situated in vibrant Ludwigsvorstadt, we are just steps away from
              the Oktoberfest grounds and minutes from the historic city center.
            </p>
          </div>
          <div class="amenity-card">
            <h3>Boutique Design</h3>
            <p>
              Each of our rooms is uniquely curated, blending classic
              architectural elements with contemporary artistic flair.
            </p>
          </div>
          <div class="amenity-card">
            <h3>Personalized Service</h3>
            <p>
              As a premier boutique destination, we pride ourselves on providing
              an intimate, attentive service tailored to every guest's journey.
            </p>
          </div>
        </div>
      </section>
    </main>
    <Appfooter />
  </div>
</template>

