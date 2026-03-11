<template>
  <div class="min-h-screen bg-[#0A0A0A] text-white font-sans selection:bg-[#D9A05B] selection:text-black">
    <!-- Navigation -->
    <header class="fixed top-0 left-0 right-0 z-50 bg-black/20 backdrop-blur-md">
      <nav class="container mx-auto px-6 h-20 flex items-center justify-between">
        <div class="flex items-center gap-2 group cursor-pointer">
          <div class="w-8 h-8 bg-gradient-to-br from-[#D9A05B] to-[#B8860B] rounded-full flex items-center justify-center">
            <span class="text-black font-bold text-xs">V</span>
          </div>
          <span class="text-xl font-bold tracking-tight group-hover:text-[#D9A05B] transition-colors">VenobHD</span>
        </div>

        <ul class="hidden md:flex items-center gap-8 text-sm font-medium text-gray-300">
          <li><a href="#" class="hover:text-[#D9A05B] transition-colors">Home</a></li>
          <li><a href="#" class="hover:text-[#D9A05B] transition-colors relative after:absolute after:bottom-[-4px] after:left-0 after:w-full after:h-[2px] after:bg-[#D9A05B]">Packages</a></li>
          <li><a href="#" class="hover:text-[#D9A05B] transition-colors">Pizza</a></li>
          <li><a href="#" class="hover:text-[#D9A05B] transition-colors">Burger</a></li>
          <li><a href="#" class="hover:text-[#D9A05B] transition-colors">Contact</a></li>
          <li><a href="#" class="hover:text-[#D9A05B] transition-colors flex items-center gap-1">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
            Sign In</a>
          </li>
        </ul>

        <button class="bg-gradient-to-r from-[#D9A05B] to-[#B8860B] text-black px-6 py-2.5 rounded-full text-sm font-bold shadow-lg shadow-orange-900/20 hover:scale-105 transition-transform">
          Contact Details
        </button>
      </nav>
    </header>

    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center pt-20 overflow-hidden">
      <!-- Decorative Background Blur -->
      <div class="absolute top-1/4 right-0 w-[500px] h-[500px] bg-orange-900/10 blur-[120px] rounded-full"></div>

      <div class="container mx-auto px-6 grid md:grid-cols-2 gap-12 items-center relative z-10">
        <div class="max-w-xl">
          <h1 class="font-serif text-6xl lg:text-7xl font-bold leading-tight mb-6">
            <span class="block">Yoan Your</span>
            <span class="block text-[#D9A05B]">Camily Home</span>
            <span class="block font-normal italic text-5xl lg:text-6xl mt-2">the Belloic High and Herms</span>
          </h1>
          <p class="text-gray-400 text-lg mb-10 leading-relaxed max-w-md">
            The flavors of our high-quality products are curated with passion to create an experience that meets your needs perfectly.
          </p>
          <div class="flex items-center gap-6">
            <button class="bg-[#D9A05B] text-black px-8 py-4 rounded-full font-bold hover:bg-[#B8860B] transition-colors flex items-center gap-2">
              Explore Our Highlights
              <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
            </button>
          </div>
        </div>

        <div class="relative group">
          <div class="absolute inset-0 bg-gradient-to-r from-orange-500/20 to-transparent blur-3xl rounded-full scale-110 lg:scale-150 transform -translate-y-10"></div>
          <div class="relative z-10 scale-110">
            <img src="/images/hero_burger.png" alt="Gourmet Burger" class="w-full max-w-lg mx-auto drop-shadow-[0_35px_35px_rgba(0,0,0,0.6)] group-hover:scale-105 transition-transform duration-700 mt-10" />

            <!-- Bottom Stats/Promo Card -->
            <div class="absolute -bottom-10 left-1/2 -translate-x-1/2 w-full max-w-md bg-black/40 backdrop-blur-xl border border-white/10 rounded-2xl p-6 flex items-center justify-between shadow-2xl">
              <div class="flex items-center gap-4">
                <div class="w-10 h-10 rounded-full border border-gray-600 flex items-center justify-center">
                   <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="15 18 9 12 15 6"></polyline></svg>
                </div>
                <div>
                  <div class="font-serif text-2xl font-bold">Gourmet</div>
                  <div class="text-xs text-gray-500 uppercase tracking-widest">Since 1978</div>
                </div>
              </div>
              <div class="h-10 w-px bg-white/10 mx-4"></div>
              <p class="text-[10px] text-gray-400 max-w-[180px] leading-tight">
                Wilshire for those who seek the best culinary and artisanal dishes. Crafted with choice ingredients and seasoned with passion.
              </p>
               <div class="w-10 h-10 rounded-full bg-[#D9A05B] flex items-center justify-center ml-4 cursor-pointer hover:rotate-45 transition-transform">
                   <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-black" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="9 18 15 12 9 6"></polyline></svg>
                </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Pagination/Nav Indicators -->
      <div class="absolute bottom-10 left-6 flex flex-col gap-4">
        <div class="w-1.5 h-1.5 rounded-full bg-white/20"></div>
        <div class="w-1.5 h-6 rounded-full bg-[#D9A05B]"></div>
        <div class="w-1.5 h-1.5 rounded-full bg-white/20"></div>
      </div>
    </section>

    <!-- Experience Section -->
    <section class="py-32 relative overflow-hidden">
        <div class="container mx-auto px-6 grid md:grid-cols-2 gap-20 items-center">
            <div class="order-2 md:order-1">
                <span class="text-[#D9A05B] text-sm font-bold tracking-[0.2em] uppercase mb-4 block">Gourmet Experience</span>
                <h2 class="font-serif text-5xl font-bold mb-8 leading-tight">
                    Immensity with<br/>
                    Sharings with 0 interest<br/>
                    to quick and elegant<br/>
                    culture.
                </h2>
                <p class="text-gray-400 text-lg leading-relaxed mb-10 max-w-md">
                    Where elegance meets taste. Our daily curated menu focuses on the best products available, ensuring a unique experience every time you visit.
                </p>
                <button class="border border-[#D9A05B] text-[#D9A05B] px-8 py-3.5 rounded-full font-bold hover:bg-[#D9A05B] hover:text-black transition-all">
                    Discover More
                </button>
            </div>
            <div class="order-1 md:order-2 relative">
                <div class="absolute inset-0 bg-orange-500/5 blur-[80px] rounded-full"></div>
                <!-- Circular Image Container to match design -->
                 <div class="relative z-10 w-full aspect-square max-w-md mx-auto overflow-hidden rounded-full border-[10px] border-white/5 p-4 bg-white/5">
                    <img src="/images/about_dish.png" alt="Featured Dish" class="w-full h-full object-cover rounded-full hover:scale-110 transition-transform duration-1000" />
                 </div>
                 <!-- Decorative arrow button like in the image -->
                 <div class="absolute bottom-10 -right-4 w-12 h-12 bg-white/10 backdrop-blur-md rounded-full flex items-center justify-center border border-white/10 text-white hover:bg-[#D9A05B] hover:text-black transition-all cursor-pointer">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="9 18 15 12 9 6"></polyline></svg>
                 </div>
            </div>
        </div>
    </section>

    <!-- Menu Section (Favorites) -->
    <section class="py-24 bg-black/50">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16">
                <span class="text-[#D9A05B] text-xs font-bold tracking-[0.3em] uppercase mb-3 block">Selected Offerings</span>
                <h2 class="font-serif text-4xl font-bold">Webfoutend</h2>
                <div class="w-16 h-1 bg-[#D9A05B] mx-auto mt-4"></div>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-8">
                <!-- Item 1 -->
                <div class="group h-full flex flex-col">
                    <div class="relative overflow-hidden rounded-2xl aspect-[4/5] mb-6">
                        <img src="/images/menu_item_1.png" alt="Seafood Highlights" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" />
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
                    </div>
                    <h3 class="font-serif text-xl font-bold mb-2">Seafront Signature</h3>
                    <p class="text-xs text-gray-500 uppercase tracking-widest mb-4">Seafood / Best Choice</p>
                    <p class="text-gray-400 text-xs leading-relaxed mb-6 line-clamp-2">
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
                    <p class="text-xs text-gray-500 uppercase tracking-widest mb-4">Meat Specialties</p>
                    <p class="text-gray-400 text-xs leading-relaxed mb-6 line-clamp-2">
                         Experience the rich, classic flavors of our handcrafted meat dishes served with premium sauces.
                    </p>
                    <button class="mt-auto px-6 py-2 border border-white/20 rounded-full text-xs font-bold group-hover:border-[#D9A05B] group-hover:text-[#D9A05B] transition-colors">
                        Explore Now
                    </button>
                </div>

                <!-- Item 3 -->
                <div class="group h-full flex flex-col md:translate-y-4">
                    <div class="relative overflow-hidden rounded-2xl aspect-[4/5] mb-6">
                        <img src="/images/menu_item_2_3_4.png" alt="Premium Steak" class="w-full h-full object-cover object-center group-hover:scale-110 transition-transform duration-700" />
                        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-60"></div>
                    </div>
                    <h3 class="font-serif text-xl font-bold mb-2">Heritage Beef</h3>
                    <p class="text-xs text-gray-500 uppercase tracking-widest mb-4">Grill / Prime Cut</p>
                    <p class="text-gray-400 text-xs leading-relaxed mb-6 line-clamp-2">
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
                    <p class="text-xs text-gray-500 uppercase tracking-widest mb-4">Signature Desserts</p>
                    <p class="text-gray-400 text-xs leading-relaxed mb-6 line-clamp-2">
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
        <div class="container mx-auto px-6 text-center text-gray-500 text-sm italic">
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
