<script setup lang="ts">
import Navbar from '../components/Navbar.vue'
</script>

<template>
  <div class="min-h-screen bg-[#0A0A0A] text-white font-sans selection:bg-[#D9A05B] selection:text-black">
    <Navbar />

    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center pt-24 pb-16 lg:pt-20 overflow-hidden">
      <!-- Decorative Background Blur -->
      <div class="absolute top-1/4 right-0 w-[300px] h-[300px] md:w-[500px] md:h-[500px] bg-orange-900/10 blur-[80px] md:blur-[120px] rounded-full"></div>

      <div class="container mx-auto px-6 grid lg:grid-cols-2 gap-12 items-center relative z-10">
        <div class="max-w-xl text-center lg:text-left lg:ml-16">
          <h1 class="font-serif text-2xl sm:text-2xl md:text-4xl lg:text-5xl font-bold leading-tight mb-6">
            <span class="block text-[#D9A05B]">Yoan Your</span>
            <span class="block text-[#D9A05B]">Camily Home</span>
            <span class="block text-[#D9A05B] font-serif font-bold  text-2xl sm:text-4xl md:text-4xl lg:text-5xl mt-2">the Belloic High <br> and Herms</span>
          </h1>
          <p class="text-gray-400 text-base md:text-lg mb-8 md:mb-10 leading-relaxed mx-auto lg:mx-0 max-w-md">
            The flavors of our high-quality products are curated with passion to create an experience that meets your needs perfectly.
          </p>
          <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4 sm:gap-6">
            <button class="w-full sm:w-auto bg-[#D9A05B] text-black px-8 py-4 rounded-full font-bold hover:bg-[#B8860B] transition-colors flex items-center justify-center gap-2">
              Explore Our Highlights
              <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
            </button>
          </div>
        </div>

        <div class="relative group mt-12 lg:mt-0 lg:mr-24 lg:mt-10">
          <div class="absolute inset-0 bg-gradient-to-r from-orange-500/10 to-transparent blur-2xl md:blur-3xl rounded-full scale-110 lg:scale-150 transform -translate-y-10"></div>
          <div class="relative z-10 scale-105 sm:scale-110">
            <img src="/images/hero_burger.png" alt="Gourmet Burger" class="w-full max-w-[320px] sm:max-w-lg mx-auto drop-shadow-[0_20px_20px_rgba(0,0,0,0.6)] lg:drop-shadow-[0_35px_35px_rgba(0,0,0,0.6)] group-hover:scale-105 transition-transform duration-700" />

            <!-- Bottom Stats/Promo Card -->
            <div class="absolute -bottom-8 sm:-bottom-10 left-1/2 -translate-x-1/2 w-[90%] sm:w-full max-w-xs sm:max-w-md bg-black/60 backdrop-blur-xl border border-white/10 rounded-2xl p-4 sm:p-6 flex items-center justify-between shadow-2xl">
              <div class="flex items-center gap-3 sm:gap-4">
                <div class="w-8 h-8 sm:w-10 sm:h-10 rounded-full border border-gray-600 flex items-center justify-center">
                   <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 sm:w-5 sm:h-5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="15 18 9 12 15 6"></polyline></svg>
                </div>
                <div>
                  <div class="font-serif text-xl sm:text-2xl font-bold">Gourmet</div>
                  <div class="text-[10px] text-gray-500 uppercase tracking-widest">Since 1978</div>
                </div>
              </div>
              <div class="h-8 sm:h-10 w-px bg-white/10 mx-2 sm:mx-4"></div>
              <p class="text-[9px] sm:text-[10px] text-gray-400 max-w-[120px] sm:max-w-[180px] leading-tight">
                Wilshire for those who seek the best culinary and artisanal dishes.
              </p>
               <div class="w-8 h-8 sm:w-10 sm:h-10 rounded-full bg-[#D9A05B] flex items-center justify-center ml-2 sm:ml-4 cursor-pointer hover:rotate-45 transition-transform">
                   <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 sm:w-5 sm:h-5 text-black" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="9 18 15 12 9 6"></polyline></svg>
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

    <!-- Experience Section -->
    <section class="py-20 md:py-32 relative overflow-hidden">
      <div class="container mx-auto px-6 grid lg:grid-cols-2 gap-12 lg:gap-20 items-center">
        <div class="order-2 lg:order-1 text-center lg:text-left">
          <span class="text-[#D9A05B] text-sm font-bold tracking-[0.2em] uppercase mb-4 block">Gourmet Experience</span>
          <h2 class="font-serif text-3xl sm:text-4xl md:text-5xl font-bold mb-6 md:mb-8 leading-tight">
            Immensity with<br />
            Sharings with 0 interest<br />
            to quick and elegant<br />
            culture.
          </h2>
          <p class="text-gray-400 text-base md:text-lg leading-relaxed mb-8 md:mb-10 mx-auto lg:mx-0 max-w-md">
            Where elegance meets taste. Our daily curated menu focuses on the best products available, ensuring a unique experience every time you visit.
          </p>
          <button class="border border-[#D9A05B] text-[#D9A05B] px-8 py-3.5 rounded-full font-bold hover:bg-[#D9A05B] hover:text-black transition-all">
            Discover More
          </button>
        </div>
        <div class="order-1 lg:order-2 relative">
          <div class="absolute inset-0 bg-orange-500/5 blur-[80px] rounded-full"></div>
          <!-- Circular Image Container -->
          <div class="relative z-10 w-full aspect-square max-w-[280px] sm:max-w-md mx-auto overflow-hidden rounded-full border-[6px] sm:border-[10px] border-white/5 p-3 sm:p-4 bg-white/5">
            <img src="/images/about_dish.png" alt="Featured Dish" class="w-full h-full object-cover rounded-full hover:scale-110 transition-transform duration-1000" />
          </div>
          <!-- Decorative arrow button -->
          <div class="absolute bottom-6 sm:bottom-10 right-0 sm:-right-4 w-10 h-10 sm:w-12 sm:h-12 bg-white/10 backdrop-blur-md rounded-full flex items-center justify-center border border-white/10 text-white hover:bg-[#D9A05B] hover:text-black transition-all cursor-pointer">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 sm:w-6 sm:h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="9 18 15 12 9 6"></polyline></svg>
          </div>
        </div>
      </div>
    </section>

    <!-- Menu Section (Favorites) -->
    <section class="py-20 md:py-24 bg-black/50">
      <div class="container mx-auto px-6">
        <div class="text-center mb-12 sm:mb-16">
          <span class="text-[#D9A05B] text-xs font-bold tracking-[0.3em] uppercase mb-3 block">Selected Offerings</span>
          <h2 class="font-serif text-3xl sm:text-4xl font-bold">Webfoutend</h2>
          <div class="w-16 h-1 bg-[#D9A05B] mx-auto mt-4"></div>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-4 gap-8">
          <!-- Item 1 -->
          <div class="group h-full flex flex-col">
            <div class="relative overflow-hidden rounded-2xl aspect-[4/5] mb-6">
              <img src="/images/menu_item_1.png" alt="Seafood Highlights" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
            </div>
            <h3 class="font-serif text-xl font-bold mb-2">Seafront Signature</h3>
            <p class="text-[10px] sm:text-xs text-gray-500 uppercase tracking-widest mb-4">Seafood / Best Choice</p>
            <p class="text-gray-400 text-xs sm:text-sm leading-relaxed mb-6 line-clamp-2">
              Wilshire for those who seek the best culinary and artisanal dishes. Crafted with choice ingredients.
            </p>
            <button class="mt-auto px-6 py-2 border border-white/20 rounded-full text-xs font-bold group-hover:border-[#D9A05B] group-hover:text-[#D9A05B] transition-colors">
              Explore Now
            </button>
          </div>

          <!-- Item 2 -->
          <div class="group h-full flex flex-col">
            <div class="relative overflow-hidden rounded-2xl aspect-[4/5] mb-6">
              <img src="/images/menu_item_2_3_4.png" alt="Gourmet Meatballs" class="w-full h-full object-cover object-left group-hover:scale-110 transition-transform duration-700" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
            </div>
            <h3 class="font-serif text-xl font-bold mb-2">Savory Meatballs</h3>
            <p class="text-[10px] sm:text-xs text-gray-500 uppercase tracking-widest mb-4">Meat Specialties</p>
            <p class="text-gray-400 text-xs sm:text-sm leading-relaxed mb-6 line-clamp-2">
               Experience the rich, classic flavors of our handcrafted meat dishes served with premium sauces.
            </p>
            <button class="mt-auto px-6 py-2 border border-white/20 rounded-full text-xs font-bold group-hover:border-[#D9A05B] group-hover:text-[#D9A05B] transition-colors">
              Explore Now
            </button>
          </div>

          <!-- Item 3 -->
          <div class="group h-full flex flex-col xl:translate-y-4">
            <div class="relative overflow-hidden rounded-2xl aspect-[4/5] mb-6">
              <img src="/images/menu_item_2_3_4.png" alt="Premium Steak" class="w-full h-full object-cover object-center group-hover:scale-110 transition-transform duration-700" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
            </div>
            <h3 class="font-serif text-xl font-bold mb-2">Heritage Beef</h3>
            <p class="text-[10px] sm:text-xs text-gray-500 uppercase tracking-widest mb-4">Grill / Prime Cut</p>
            <p class="text-gray-400 text-xs sm:text-sm leading-relaxed mb-6 line-clamp-2">
              Premium cuts of beef, dry-aged and grilled to perfection over natural wood fire.
            </p>
            <button class="mt-auto px-6 py-2 border border-white/20 rounded-full text-xs font-bold group-hover:border-[#D9A05B] group-hover:text-[#D9A05B] transition-colors">
              Explore Now
            </button>
          </div>

          <!-- Item 4 -->
          <div class="group h-full flex flex-col">
            <div class="relative overflow-hidden rounded-2xl aspect-[4/5] mb-6">
              <img src="/images/menu_item_2_3_4.png" alt="Artisan Dessert" class="w-full h-full object-cover object-right group-hover:scale-110 transition-transform duration-700" />
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
            </div>
            <h3 class="font-serif text-xl font-bold mb-2">Velvet Sweetness</h3>
            <p class="text-[10px] sm:text-xs text-gray-500 uppercase tracking-widest mb-4">Signature Desserts</p>
            <p class="text-gray-400 text-xs sm:text-sm leading-relaxed mb-6 line-clamp-2">
              A perfect end to your meal. Delicate desserts crafted by our master pastry chefs.
            </p>
            <button class="mt-auto px-6 py-2 border border-white/20 rounded-full text-xs font-bold group-hover:border-[#D9A05B] group-hover:text-[#D9A05B] transition-colors">
              Explore Now
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 border-t border-white/5 bg-black">
      <div class="container mx-auto px-6 text-center text-gray-500 text-xs sm:text-sm italic">
        &copy; 2026 VenobHD. Designed for the ultimate gourmet experience.
      </div>
    </footer>
  </div>
</template>

<style scoped>
.aspect-\[4\/5\] {
  aspect-ratio: 4 / 5;
}
</style>
