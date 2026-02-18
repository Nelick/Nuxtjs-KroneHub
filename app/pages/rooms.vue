```vue
<script setup lang="ts">
import "../assets/style.css";
import Appheader from "../components/Appheader.vue";
import Appfooter from "../components/Appfooter.vue";

const rooms = [
  {
    name: "Standard Room",
    price: "120",
    image: "https://images.unsplash.com/photo-1582719478250-c89ea26ee158?w=1200&h=800&fit=crop",
    description: "Experience comfort and style in our Standard Rooms. Featuring plush bedding and views of the vibrant Ludwigsvorstadt district.",
    amenities: ["Free WiFi", "24/7 Service", "Breakfast Included", "City View"]
  }
];
</script>

<template>
  <div class="bg-[#fcfbf7] min-h-screen font-sans selection:bg-amber-100">
    <Appheader />
    
    <main class="max-w-6xl mx-auto px-6 py-20 lg:py-32">
      <!-- Hero -->
      <header class="mb-20 animate-in fade-in slide-in-from-bottom-4 duration-1000">
        <p class="text-amber-800 tracking-widest text-xs uppercase mb-4">Munich's Hidden Gem</p>
        <h1 class="text-4xl md:text-6xl font-serif text-stone-900 leading-tight max-w-2xl">
          Refined Living at Boutique Hotel Krone
        </h1>
      </header>

      <!-- Room Grid -->
      <div class="space-y-32">
        <section 
          v-for="room in rooms" 
          :key="room.name"
          class="grid lg:grid-cols-2 gap-12 items-center group"
        >
          <div class="overflow-hidden rounded-sm aspect-[4/3] bg-stone-100 animate-in fade-in zoom-in-95 duration-700">
            <img
              :src="room.image"
              :alt="room.name"
              class="w-full h-full object-cover grayscale-[0.2] group-hover:grayscale-0 group-hover:scale-105 transition-all duration-700 ease-out"
            />
          </div>

          <div class="space-y-8 animate-in fade-in slide-in-from-right-8 duration-700 delay-150">
            <div>
              <h2 class="text-3xl font-serif text-stone-900 mb-4">{{ room.name }}</h2>
              <p class="text-stone-500 leading-relaxed max-w-md">
                {{ room.description }}
              </p>
            </div>

            <ul class="grid grid-cols-2 gap-y-3 gap-x-6 text-sm text-stone-600">
              <li v-for="item in room.amenities" :key="item" class="flex items-center gap-2">
                <span class="w-1 h-1 rounded-full bg-amber-800"></span>
                {{ item }}
              </li>
            </ul>

            <div class="flex items-center gap-8 pt-6">
              <div>
                <span class="text-xs uppercase tracking-tighter text-stone-400 block">From</span>
                <span class="text-2xl font-serif text-stone-900">€{{ room.price }}</span>
              </div>
              <button class="px-10 py-4 bg-stone-900 text-white text-sm uppercase tracking-widest hover:bg-amber-900 transition-colors duration-300">
                Book Now
              </button>
            </div>
          </div>
        </section>
      </div>
    </main>

    <Appfooter />
  </div>
</template>

<style scoped>
@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slide-in-from-bottom {
  from { transform: translateY(20px); }
  to { transform: translateY(0); }
}

@keyframes slide-in-from-right {
  from { transform: translateX(20px); }
  to { transform: translateX(0); }
}

.animate-in {
  animation-fill-mode: both;
}

.fade-in { animation-name: fade-in; }
.slide-in-from-bottom-4 { animation-name: slide-in-from-bottom; }
.slide-in-from-right-8 { animation-name: slide-in-from-right; }

.duration-700 { animation-duration: 700ms; }
.duration-1000 { animation-duration: 1000ms; }
.delay-150 { animation-delay: 150ms; }
</style>
```
