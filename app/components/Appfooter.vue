
<script setup lang="ts">
import "../assets/style.css";
</script>

<template>
  <footer class="bg-stone-900 text-stone-300 py-16 font-sans antialiased">
    <div class="max-w-7xl mx-auto px-6 grid grid-cols-1 md:grid-cols-3 gap-12">
      <div class="space-y-4">
        <h2 class="text-white text-2xl font-serif italic">
          Boutique Hotel Krone
        </h2>
        <p class="text-sm leading-relaxed max-w-xs">
          Experience timeless elegance and Bavarian charm at the gates of the
          Theresienwiese. Your sanctuary in the heart of Munich.
        </p>
      </div>

      <div class="space-y-4">
        <h3 class="text-white font-medium uppercase tracking-widest text-xs">
          Contact & Location
        </h3>
        <address class="not-italic text-sm space-y-2">
          <p>Theresienhöhe 8<br />80339 Munich, Germany</p>
          <p>
            T:
            <a
              href="tel:+4989510880"
              class="hover:text-white transition-colors"
              >+49 (0) 89 510 88 0</a
            >
          </p>
          <p>
            E:
            <a
              href="mailto:info@hotel-krone-muenchen.de"
              class="hover:text-white transition-colors"
              >info@hotel-krone-muenchen.de</a
            >
          </p>
        </address>
      </div>

      <div class="space-y-4">
        <h3 class="text-white font-medium uppercase tracking-widest text-xs">
          Navigation
        </h3>
        <nav class="flex flex-col space-y-2 text-sm">
          <NuxtLink to="/rooms" class="hover:text-white transition-colors"
            >Rooms & Suites</NuxtLink
          >
          <NuxtLink
            to="/breakfast"
            class="hover:text-white transition-colors"
            >Breakfast</NuxtLink
          >
          <NuxtLink to="/imprint" class="hover:text-white transition-colors"
            >Imprint</NuxtLink
          >
          <NuxtLink to="/privacy" class="hover:text-white transition-colors"
            >Privacy Policy</NuxtLink
          >
        </nav>
      </div>
    </div>

    <div
      class="max-w-7xl mx-auto px-6 mt-16 pt-8 border-t border-stone-800 flex flex-col md:flex-row justify-between items-center gap-4 text-[10px] uppercase tracking-widest text-stone-500"
    >
      <p>&copy; {{ new Date().getFullYear() }} Boutique Hotel Krone Munich</p>
      <div class="flex gap-8">
        <a href="#" class="hover:text-white transition-colors">Instagram</a>
        <a href="#" class="hover:text-white transition-colors">Facebook</a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
footer {
  font-family: "Inter", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.font-serif {
  font-family: "Playfair Display", serif;
}
</style>
