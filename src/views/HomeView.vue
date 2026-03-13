<script setup lang="ts">
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'
</script>

<template>
  <div class="min-h-screen bg-[#0A0A0A] text-white font-sans selection:bg-[#D9A05B] selection:text-black">
    <Navbar />

    <!-- Hero Section -->
    <section class="relative min-h-[90vh] flex items-center pt-24 pb-16 lg:pt-20 overflow-hidden">
      <!-- Premium Atmospheric Backgrounds -->
      <div class="absolute top-[10%] right-[-5%] w-[40vw] h-[40vw] bg-[#D9A05B]/10 blur-[120px] rounded-full animate-pulse-slow"></div>
      <div class="absolute bottom-[10%] left-[-5%] w-[30vw] h-[30vw] bg-[#D9A05B]/5 blur-[100px] rounded-full"></div>
      
      <!-- Subtle Grid Overlay -->
      <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MCIgaGVpZ2h0PSI0MCIgdmlld0JveD0iMCAwIDQwIDQwIj48ZyBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiPjxnIGZpbGw9IiNhYWEiIGZpbGwtb3BhY2l0eT0iMC4wNSI+PHBhdGggZD0iTTAgMGg0MHY0MEgwVjB6bTEgMWgzOHYzOEgxVjF6Ii8+PC9nPjwvZz48L3N2Zz4=')] opacity-20"></div>

      <div class="container mx-auto px-6 grid lg:grid-cols-2 gap-12 items-center relative z-10">
        <div class="max-w-xl text-center lg:text-left lg:ml-8 reveal-fade-in">
          <div class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-white/5 border border-white/10 mb-6 backdrop-blur-sm">
            <span class="w-1.5 h-1.5 rounded-full bg-[#D9A05B] animate-ping"></span>
            <span class="text-[9px] font-bold text-[#D9A05B] uppercase tracking-[0.25em]">The New Era of Hospitality</span>
          </div>
          
          <h1 class="font-syne text-4xl md:text-5xl lg:text-6xl font-extrabold leading-[1.1] mb-6 text-white">
            Where <span class="italic text-[#D9A05B] drop-shadow-[0_0_20px_rgba(217,160,91,0.2)]">Elegance</span><br />
            Meets Operations.
          </h1>
          
          <p class="text-gray-400 text-base md:text-lg mb-8 leading-relaxed max-w-md mx-auto lg:mx-0 font-outfit font-light">
            Elevate your establishment with a management ecosystem designed for the world's most sophisticated culinary brands.
          </p>
          <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4">
            <button
              class="w-full sm:w-auto bg-[#D9A05B] text-black px-7 py-3 rounded-full text-sm font-bold hover:bg-[#B8860B] transition-colors flex items-center justify-center gap-2">
              Explore the Platform
              <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 24 24" fill="none"
                stroke="currentColor" stroke-width="2.5">
                <line x1="5" y1="12" x2="19" y2="12"></line>
                <polyline points="12 5 19 12 12 19"></polyline>
              </svg>
            </button>
          </div>
        </div>

        <div class="relative group mt-12 lg:mt-0 lg:mr-24 lg:mt-10">
          <div
            class="absolute inset-0 bg-gradient-to-r from-orange-500/10 to-transparent blur-2xl md:blur-3xl rounded-full scale-110 lg:scale-150 transform -translate-y-10">
          </div>
          <div class="relative z-10 scale-105 sm:scale-110">
            <img src="/images/hero_burger.png" alt="Gourmet Burger"
              class="w-full max-w-[320px] sm:max-w-lg mx-auto drop-shadow-[0_20px_20px_rgba(0,0,0,0.6)] lg:drop-shadow-[0_35px_35px_rgba(0,0,0,0.6)] group-hover:scale-105 transition-transform duration-700" />

            <!-- Bottom Stats/Promo Card -->
            <div
              class="absolute -bottom-8 sm:-bottom-10 left-1/2 -translate-x-1/2 w-[90%] sm:w-full max-w-xs sm:max-w-md bg-black/60 backdrop-blur-xl border border-white/10 rounded-2xl p-4 sm:p-6 flex items-center justify-between shadow-2xl">
              <div class="flex items-center gap-3 sm:gap-4">
                <div
                  class="w-8 h-8 sm:w-10 sm:h-10 rounded-full border border-gray-600 flex items-center justify-center">
                  <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 sm:w-5 sm:h-5 text-gray-400"
                    viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <polyline points="15 18 9 12 15 6"></polyline>
                  </svg>
                </div>
                <div>
                  <div class="font-serif text-xl sm:text-2xl font-bold text-white">Gourmet</div>
                  <div class="text-[10px] text-[#D9A05B] uppercase tracking-widest font-bold">Since 2026</div>
                </div>
              </div>
              <div class="h-8 sm:h-10 w-px bg-white/10 mx-2 sm:mx-4"></div>
              <p class="text-[9px] sm:text-[10px] text-gray-400 max-w-[120px] sm:max-w-[180px] leading-tight">
                Designed for those who seek the best culinary control and artisanal efficiency.
              </p>
              <div
                class="w-8 h-8 sm:w-10 sm:h-10 rounded-full bg-[#D9A05B] flex items-center justify-center ml-2 sm:ml-4 cursor-pointer hover:rotate-45 transition-transform">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 sm:w-5 sm:h-5 text-black" viewBox="0 0 24 24"
                  fill="none" stroke="currentColor" stroke-width="2">
                  <polyline points="9 18 15 12 9 6"></polyline>
                </svg>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Pagination/Nav Indicators -->
      <div class="absolute bottom-10 left-6 hidden sm:flex flex-col gap-4">
        <div class="w-1.5 h-1.5 rounded-full bg-white/20"></div>
        <div class="w-1.5 h-6 rounded-full bg-[#D9A05B]"></div>
        <div class="w-1.5 h-1.5 rounded-full bg-white/20"></div>
      </div>
    </section>

      <Navbar />

    <!-- Metrics Ribbon -->
    <div class="relative z-20 -mt-8 mb-16">
      <div class="container mx-auto px-6 max-w-5xl">
        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 p-6 rounded-[2rem] bg-white/[0.03] border border-white/10 backdrop-blur-2xl shadow-xl reveal-fade-in">
          <div class="text-center space-y-1">
            <div class="text-2xl font-syne font-extrabold text-[#D9A05B]">500+</div>
            <div class="text-[9px] text-gray-500 uppercase tracking-widest font-bold">Luxury Brands</div>
          </div>
          <div class="text-center space-y-1 border-l border-white/5">
            <div class="text-2xl font-syne font-extrabold text-white">1.2M</div>
            <div class="text-[9px] text-gray-500 uppercase tracking-widest font-bold">Orders/Mo</div>
          </div>
          <div class="text-center space-y-1 border-l border-white/5">
            <div class="text-2xl font-syne font-extrabold text-[#D9A05B]">99.9%</div>
            <div class="text-[9px] text-gray-500 uppercase tracking-widest font-bold">System Uptime</div>
          </div>
          <div class="text-center space-y-1 border-l border-white/5">
            <div class="text-2xl font-syne font-extrabold text-white">24/7</div>
            <div class="text-[9px] text-gray-500 uppercase tracking-widest font-bold">Elite Support</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Experience Section (Glassmorphism Upgrade) -->
    <section class="py-16 relative overflow-hidden">
      <div class="container mx-auto px-6 grid lg:grid-cols-2 gap-16 items-center">
        <div class="order-2 lg:order-1 text-center lg:text-left reveal-fade-in">
          <span class="text-[#D9A05B] text-[10px] font-bold tracking-[0.3em] uppercase mb-4 block">Empowering Excellence</span>
          <h2 class="font-syne text-3xl md:text-4xl font-extrabold mb-6 leading-tight text-white">
            Immense Control.<br />
            Seamless Flow.
          </h2>
          <p class="text-gray-400 text-base leading-relaxed mb-8 mx-auto lg:mx-0 max-w-sm font-outfit font-light">
            Where efficiency meets the art of hospitality. Our suite is engineered to vanish into your workflow, leaving only pure performance.
          </p>
          <div class="flex flex-wrap justify-center lg:justify-start gap-4">
            <button class="px-7 py-3 rounded-full bg-white/5 border border-white/10 text-white text-sm font-bold hover:border-[#D9A05B]/40 hover:bg-[#D9A05B]/10 transition-all">
              Explore Toolkit
            </button>
          </div>
        </div>
        <div class="order-1 lg:order-2 relative group reveal-fade-in">
          <div class="absolute inset-0 bg-[#D9A05B]/5 blur-[80px] rounded-full group-hover:bg-[#D9A05B]/10 transition-all duration-1000"></div>
          <div class="relative z-10 w-full aspect-square max-w-sm mx-auto rounded-[2.5rem] overflow-hidden border border-white/10 bg-white/5 p-3 backdrop-blur-3xl shadow-2xl">
            <img src="/images/about_dish.png" alt="Featured Dish" class="w-full h-full object-cover rounded-[2rem] group-hover:scale-105 transition-transform duration-1000" />
            
            <!-- Glass Overlay Card -->
            <div class="absolute bottom-6 left-6 right-6 p-4 rounded-xl bg-black/40 backdrop-blur-xl border border-white/10 transform translate-y-3 opacity-0 group-hover:translate-y-0 group-hover:opacity-100 transition-all duration-500">
              <div class="text-[#D9A05B] text-[9px] font-bold uppercase tracking-widest mb-1">Signature Experience</div>
              <div class="text-white font-syne font-bold text-base">Seamless Guest Journey</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Culinary Excellence (Strategic Imagery) -->
    <section class="py-24 relative group overflow-hidden">
      <div class="absolute inset-0 z-0">
        <img src="/images/staff_feature.png" alt="Kitchen Mastery" class="w-full h-full object-cover opacity-30 grayscale group-hover:grayscale-0 group-hover:opacity-40 transition-all duration-1000 scale-105" />
        <div class="absolute inset-0 bg-gradient-to-b from-[#0A0A0A] via-transparent to-[#0A0A0A]"></div>
      </div>
      
      <div class="container mx-auto px-6 relative z-10">
        <div class="max-w-3xl mx-auto text-center space-y-10">
          <div class="space-y-3">
             <span class="text-[#D9A05B] text-[10px] font-bold tracking-[0.4em] uppercase">Core Philosophy</span>
             <h2 class="font-syne text-3xl md:text-5xl font-extrabold text-white">The Rhythm of a High-Performance Kitchen.</h2>
          </div>
          <p class="text-gray-400 text-lg font-outfit font-light leading-relaxed">
            We don't just build software. We architect the synchronization between chef, server, and guest. From sub-second order firing to real-time inventory intelligence, trerazGo is the silent partner in your success.
          </p>
          <div class="pt-6">
            <button class="px-8 py-4 rounded-full bg-[#D9A05B] text-black font-extrabold tracking-widest uppercase text-[10px] shadow-xl hover:bg-[#FFE4AD] transition-all">
              Watch the Experience
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Menu Section (Favorites) -->
    <section class="py-20 bg-white/[0.01] border-y border-white/5 relative overflow-hidden">
      <!-- Decorative Background Text -->
      <div class="absolute top-0 right-0 text-[15rem] font-syne font-extrabold text-white/[0.02] leading-none pointer-events-none translate-x-1/2 -translate-y-1/4">MENU</div>
      
      <div class="container mx-auto px-6 relative z-10">
        <div class="text-center mb-16 space-y-3 reveal-fade-in">
          <span class="text-[#D9A05B] text-[10px] font-bold tracking-[0.3em] uppercase">Selected Offerings</span>
          <h2 class="font-syne text-3xl md:text-4xl font-extrabold text-white">Curated Highlights</h2>
          <div class="w-12 h-1 bg-[#D9A05B] mx-auto rounded-full"></div>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-4 gap-8">
          <!-- Item 1 -->
          <div class="group h-full flex flex-col reveal-fade-in" style="animation-delay: 0.1s">
            <div class="relative overflow-hidden rounded-[2rem] aspect-[4/5] mb-6 border border-white/10 shadow-3xl">
              <img src="/images/menu_item_1.png" alt="Seafood Highlights" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-1000" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
              <div class="absolute top-6 right-6 px-3 py-1 bg-white/10 backdrop-blur-md border border-white/20 rounded-full text-[10px] text-[#D9A05B] font-bold uppercase tracking-widest">Seafood</div>
            </div>
            <h3 class="font-syne text-xl font-bold mb-2 text-white">Seafront Signature</h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 line-clamp-2 font-outfit font-light">
              Wilshire for those who seek the best culinary and artisanal dishes. Crafted with choice ingredients.
            </p>
            <button class="mt-auto px-8 py-3 border border-white/10 bg-white/5 rounded-full text-xs font-bold hover:border-[#D9A05B]/40 hover:text-[#D9A05B] transition-all">
              Explore Now
            </button>
          </div>

          <!-- Item 2 -->
          <div class="group h-full flex flex-col reveal-fade-in" style="animation-delay: 0.2s">
            <div class="relative overflow-hidden rounded-[2rem] aspect-[4/5] mb-6 border border-white/10 shadow-3xl">
              <img src="/images/menu_item_2_3_4.png" alt="Gourmet Meatballs" class="w-full h-full object-cover object-left group-hover:scale-110 transition-transform duration-1000" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
              <div class="absolute top-6 right-6 px-3 py-1 bg-white/10 backdrop-blur-md border border-white/20 rounded-full text-[10px] text-[#D9A05B] font-bold uppercase tracking-widest">Meat</div>
            </div>
            <h3 class="font-syne text-xl font-bold mb-2 text-white">Savory Meatballs</h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 line-clamp-2 font-outfit font-light">
              Experience the rich, classic flavors of our handcrafted meat dishes served with premium sauces.
            </p>
            <button class="mt-auto px-8 py-3 border border-white/10 bg-white/5 rounded-full text-xs font-bold hover:border-[#D9A05B]/40 hover:text-[#D9A05B] transition-all">
              Explore Now
            </button>
          </div>

          <!-- Item 3 -->
          <div class="group h-full flex flex-col xl:translate-y-6 reveal-fade-in" style="animation-delay: 0.3s">
            <div class="relative overflow-hidden rounded-[2rem] aspect-[4/5] mb-6 border border-white/10 shadow-3xl">
              <img src="/images/menu_item_2_3_4.png" alt="Premium Steak" class="w-full h-full object-cover object-center group-hover:scale-110 transition-transform duration-1000" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
              <div class="absolute top-6 right-6 px-3 py-1 bg-white/10 backdrop-blur-md border border-white/20 rounded-full text-[10px] text-[#D9A05B] font-bold uppercase tracking-widest">Prime</div>
            </div>
            <h3 class="font-syne text-xl font-bold mb-2 text-white">Heritage Beef</h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 line-clamp-2 font-outfit font-light">
              Premium cuts of beef, dry-aged and grilled to perfection over natural wood fire.
            </p>
            <button class="mt-auto px-8 py-3 border border-white/10 bg-white/5 rounded-full text-xs font-bold hover:border-[#D9A05B]/40 hover:text-[#D9A05B] transition-all">
              Explore Now
            </button>
          </div>

          <!-- Item 4 -->
          <div class="group h-full flex flex-col reveal-fade-in" style="animation-delay: 0.4s">
            <div class="relative overflow-hidden rounded-[2rem] aspect-[4/5] mb-6 border border-white/10 shadow-3xl">
              <img src="/images/menu_item_2_3_4.png" alt="Artisan Dessert" class="w-full h-full object-cover object-right group-hover:scale-110 transition-transform duration-1000" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
              <div class="absolute top-6 right-6 px-3 py-1 bg-white/10 backdrop-blur-md border border-white/20 rounded-full text-[10px] text-[#D9A05B] font-bold uppercase tracking-widest">Sweet</div>
            </div>
            <h3 class="font-syne text-xl font-bold mb-2 text-white">Velvet Sweetness</h3>
            <p class="text-gray-500 text-sm leading-relaxed mb-6 line-clamp-2 font-outfit font-light">
              A perfect end to your meal. Delicate desserts crafted by our master pastry chefs.
            </p>
            <button class="mt-auto px-8 py-3 border border-white/10 bg-white/5 rounded-full text-xs font-bold hover:border-[#D9A05B]/40 hover:text-[#D9A05B] transition-all">
              Explore Now
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonial Section -->
    <section class="py-24 relative">
      <div class="container mx-auto px-6">
        <div class="max-w-3xl mx-auto">
          <div class="relative p-10 md:p-14 rounded-[2.5rem] bg-gradient-to-br from-white/[0.03] to-transparent border border-white/10 text-center space-y-8 backdrop-blur-3xl overflow-hidden reveal-fade-in">
            <div class="absolute top-0 left-0 w-full h-[2px] bg-gradient-to-r from-transparent via-[#D9A05B]/40 to-transparent"></div>
            
            <div class="flex items-center justify-center gap-1">
              <span v-for="i in 5" :key="i" class="text-[#D9A05B] text-lg">★</span>
            </div>

            <blockquote class="text-xl md:text-2xl font-syne font-medium text-white italic leading-snug">
              "The transition to ትዕዛዝGo wasn't just a software upgrade—it was a total transformation of our guest experience. Our margins increased by 22% in the first quarter."
            </blockquote>

            <div class="space-y-1">
              <cite class="text-[#D9A05B] font-syne font-extrabold not-italic uppercase tracking-[0.2em] text-[10px]">Marcus V. Sterling</cite>
              <p class="text-gray-500 text-[8px] font-bold uppercase tracking-widest">Director, The Gilded Table</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <Footer />
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@200;300;400;500;600;700&family=Syne:ital,wght@0,700;0,800;1,700;1,800&display=swap');

.font-syne { font-family: 'Syne', sans-serif; }
.font-outfit { font-family: 'Outfit', sans-serif; }

.aspect-\[4\/5\] {
  aspect-ratio: 4 / 5;
}

/* Scroll Reveal Animations */
.reveal-fade-in {
  animation: revealFadeIn 1.2s cubic-bezier(0.22, 1, 0.36, 1) forwards;
}

@keyframes revealFadeIn {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes pulse-slow {
  0%, 100% { opacity: 0.5; transform: scale(1); }
  50% { opacity: 0.8; transform: scale(1.1); }
}

.animate-pulse-slow {
  animation: pulse-slow 8s ease-in-out infinite;
}
</style>
