<script setup lang="ts">
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'
</script>

<template>
  <div class="about-page min-h-screen bg-[#0A0A0A] selection:bg-[#D9A05B] selection:text-black relative overflow-x-hidden">
    <!-- Background Elements -->
    <div class="fixed inset-0 z-0">
      <div class="absolute inset-0 bg-gradient-to-b from-[#1a1710] via-[#0A0A0A] to-[#0A0A0A]"></div>
      <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-[600px] bg-[radial-gradient(circle_at_center,rgba(217,160,91,0.08)_0%,transparent_70%)] pointer-events-none"></div>
    </div>

    <Navbar />

    <!-- Hero Section -->
    <section class="relative pt-48 pb-32 px-6 overflow-hidden">
      <div class="container mx-auto max-w-4xl relative z-10 text-center">
        <h1 class="text-5xl md:text-7xl font-serif text-white mb-6">
          Our <span class="bg-gradient-to-r from-[#D9A05B] to-[#FFE4AD] bg-clip-text text-transparent">Story</span>
        </h1>
        <p class="text-xl md:text-2xl text-white/70 max-w-2xl mx-auto font-light leading-relaxed">
          We're on a mission to bridge the gap between traditional hospitality and modern technology, creating seamless dining experiences that delight both guests and owners.
        </p>
      </div>
    </section>

    <!-- Mission & Vision -->
    <section class="py-24 px-6 relative z-10 border-t border-white/5">
      <div class="container mx-auto max-w-6xl">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-16 items-center">
          <div class="space-y-8">
            <div>
              <h2 class="text-3xl font-bold text-white mb-4 font-serif">The Vision</h2>
              <p class="text-gray-400 leading-relaxed">
                Imagine a world where ordering your favorite coffee is as quick as a scan. No waiting for menus, no miscommunication—just pure, effortless enjoyment. That's the world ትዕዛዝGo is building.
              </p>
            </div>
            <div class="grid grid-cols-2 gap-8">
              <div class="p-6 rounded-2xl bg-white/[0.02] border border-white/5">
                <div class="text-3xl font-bold text-[#D9A05B] mb-2">500+</div>
                <div class="text-gray-500 text-xs uppercase tracking-widest">Active Cafés</div>
              </div>
              <div class="p-6 rounded-2xl bg-white/[0.02] border border-white/5">
                <div class="text-3xl font-bold text-[#D9A05B] mb-2">1M+</div>
                <div class="text-gray-500 text-xs uppercase tracking-widest">Orders Processed</div>
              </div>
            </div>
          </div>
          <div class="relative">
            <div class="aspect-square rounded-3xl overflow-hidden border border-white/10 relative group">
               <div class="absolute inset-0 bg-[#D9A05B]/10 mix-blend-overlay"></div>
               <img src="/C:/Users/tiegi/.gemini/antigravity/brain/d8f66ed3-9d28-4917-8101-140ce8738b00/gourmet_restaurant_background_1773300387743.png" class="w-full h-full object-cover grayscale opacity-50 group-hover:grayscale-0 group-hover:opacity-100 transition-all duration-700" alt="Our Workspace" />
               <div class="absolute inset-0 bg-gradient-to-t from-[#0A0A0A] to-transparent"></div>
            </div>
            <!-- Decorative Elements -->
            <div class="absolute -top-12 -right-12 w-48 h-48 bg-[#D9A05B]/10 blur-[60px] rounded-full"></div>
            <div class="absolute -bottom-12 -left-12 w-48 h-48 bg-[#D9A05B]/10 blur-[60px] rounded-full"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Values Section -->
    <section class="py-24 px-6 relative z-10 bg-[#080808]">
      <div class="container mx-auto max-w-6xl text-center">
        <h2 class="text-3xl md:text-5xl font-bold text-white mb-16 font-serif">Core Values</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div class="p-10 rounded-3xl bg-[#111111] border border-white/5 hover:border-[#D9A05B]/30 transition-all">
            <div class="w-14 h-14 bg-[#D9A05B]/10 rounded-xl flex items-center justify-center mb-8 mx-auto">
              <span class="text-2xl">✨</span>
            </div>
            <h3 class="text-xl font-bold text-white mb-4">Innovation First</h3>
            <p class="text-gray-500 text-sm leading-relaxed">Always pushing the boundaries of what's possible in hospitality tech.</p>
          </div>
          <div class="p-10 rounded-3xl bg-[#111111] border border-white/5 hover:border-[#D9A05B]/30 transition-all">
            <div class="w-14 h-14 bg-[#D9A05B]/10 rounded-xl flex items-center justify-center mb-8 mx-auto">
              <span class="text-2xl">🤝</span>
            </div>
            <h3 class="text-xl font-bold text-white mb-4">Partner Success</h3>
            <p class="text-gray-500 text-sm leading-relaxed">We measure our success by the growth and happiness of our cafés.</p>
          </div>
          <div class="p-10 rounded-3xl bg-[#111111] border border-white/5 hover:border-[#D9A05B]/30 transition-all">
            <div class="w-14 h-14 bg-[#D9A05B]/10 rounded-xl flex items-center justify-center mb-8 mx-auto">
              <span class="text-2xl">🛡️</span>
            </div>
            <h3 class="text-xl font-bold text-white mb-4">Security & Reliability</h3>
            <p class="text-gray-500 text-sm leading-relaxed">Building systems that never fail, because your business never stops.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <Footer />
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Inter:wght@400;500;600;700&display=swap');

.about-page {
  font-family: 'Inter', sans-serif;
  scrollbar-width: thin;
  scrollbar-color: #D9A05B transparent;
}

.about-page .font-serif {
  font-family: 'Playfair Display', serif;
}

.about-page::-webkit-scrollbar {
  width: 6px;
}

.about-page::-webkit-scrollbar-thumb {
  background-color: #D9A05B;
  border-radius: 10px;
}
</style>
