<script setup lang="ts">
import { RouterLink } from 'vue-router'

const socialLinks = [
  { name: 'Facebook', icon: 'M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z', url: '#' },
  { name: 'Instagram', icon: 'M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z M17.5 6.5h.01', url: '#' },
  { name: 'Twitter', icon: 'M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z', url: '#' },
  { name: 'LinkedIn', icon: 'M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z M2 9h4v12H2z M4 2a2 2 0 1 1-2 2 2 2 0 0 1 2-2z', url: '#' }
]

const footerNav = [
  {
    title: 'Discover',
    links: [
      { name: 'Home', to: '/' },
      { name: 'Features', to: '#' },
      { name: 'Pricing', to: '/pricing' },
      { name: 'Menu Demo', to: '/menu' }
    ]
  },
  {
    title: 'Platform',
    links: [
      { name: 'How it Works', to: '#' },
      { name: 'QR System', to: '#' },
      { name: 'Dashboard', to: '#' },
      { name: 'Builder', to: '#' }
    ]
  },
  {
    title: 'Company',
    links: [
      { name: 'About Us', to: '/about' },
      { name: 'Contact', to: '/contact' },
      { name: 'Legal', to: '#' },
      { name: 'Partners', to: '#' }
    ]
  }
]
</script>

<template>
  <footer class="footer-premium relative bg-transparent pt-16 pb-8 overflow-hidden border-t border-[#D9A05B]/10 font-outfit">
    <!-- Distinct Background Image with Deep Overlay -->
    <div class="absolute inset-0 pointer-events-none -z-10 bg-black">
      <img src="/images/premium_footer_bg.png" 
           class="w-full h-full object-cover opacity-60 scale-105" alt="">
      <div class="absolute inset-0 bg-gradient-to-b from-black/60 via-black/20 to-black/80"></div>
      <div class="absolute top-0 left-1/4 w-[400px] h-[400px] bg-[#D9A05B]/10 rounded-full blur-[100px]"></div>
    </div>

    <div class="container mx-auto px-6 relative z-10">
      <!-- Newsletter Glass Card - Compact Version -->
      <div class="newsletter-card mb-16 p-6 md:p-8 rounded-[2rem] bg-gradient-to-br from-white/[0.04] to-transparent border border-white/5 backdrop-blur-2xl relative group overflow-hidden">
        <div class="absolute top-0 left-0 w-full h-[1px] bg-gradient-to-r from-transparent via-[#D9A05B]/30 to-transparent"></div>
        
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
          <div class="space-y-2">
            <h3 class="text-2xl md:text-3xl font-syne font-extrabold text-white leading-tight">
              Ready to <span class="bg-gradient-to-r from-[#D9A05B] to-[#FFE4AD] bg-clip-text text-transparent">Elevate?</span>
            </h3>
            <p class="text-[#E8B86D]/60 text-sm font-light">Join the future of dining experience.</p>
          </div>
          
          <div class="relative max-w-sm ml-auto w-full">
            <input 
              type="email" 
              placeholder="Email address..."
              class="w-full bg-black/50 border border-[#D9A05B]/20 rounded-xl px-5 py-3.5 pr-28 text-sm text-white focus:outline-none focus:border-[#D9A05B]/50 transition-all placeholder:text-[#E8B86D]/20 shadow-xl"
            />
            <button class="absolute right-1.5 top-1.5 bottom-1.5 px-6 bg-gradient-to-r from-[#E8B86D] to-[#B8860B] rounded-lg text-black font-bold text-xs shadow-lg hover:shadow-[#D9A05B]/20 hover:scale-105 active:scale-95 transition-all">
              Join
            </button>
          </div>
        </div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-12 gap-10 mb-16">
        <!-- Brand identity - More Compact -->
        <div class="lg:col-span-4 space-y-6">
          <RouterLink to="/" class="group flex items-center gap-3">
            <div class="relative">
              <div class="absolute inset-0 bg-[#D9A05B] blur-md opacity-20 group-hover:opacity-40 transition-opacity"></div>
              <img src="/tLogo.jpg" alt="Logo" class="w-10 h-10 object-contain rounded-xl border border-white/10 relative z-10 group-hover:rotate-6 transition-transform">
            </div>
            <div>
              <h2 class="text-2xl font-syne font-bold text-white tracking-tighter">ትዕዛዝ<span class="text-[#D9A05B]">Go</span></h2>
              <p class="text-[8px] uppercase tracking-[0.4em] text-[#D9A05B]/50 font-medium">The Gold Standard</p>
            </div>
          </RouterLink>
          
          <p class="text-[#E8B86D]/60 leading-relaxed font-light text-base italic max-w-xs">
            "Software as elegant as your finest service."
          </p>

          <div class="flex gap-3">
            <a v-for="social in socialLinks" :key="social.name" :href="social.url"
               class="w-10 h-10 rounded-xl bg-white/[0.03] border border-white/5 flex items-center justify-center text-[#D9A05B]/40 hover:text-[#D9A05B] hover:border-[#D9A05B]/20 hover:bg-[#D9A05B]/5 transition-all">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <path :d="social.icon"></path>
              </svg>
            </a>
          </div>
        </div>

        <!-- Navigation - Tighter Spacing -->
        <div class="lg:col-span-8 grid grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="group in footerNav" :key="group.title" class="space-y-6">
            <h4 class="text-[11px] font-bold uppercase tracking-[0.2em] text-[#D9A05B] font-syne opacity-80">{{ group.title }}</h4>
            <ul class="space-y-3.5">
              <li v-for="link in group.links" :key="link.name">
                <RouterLink 
                  :to="link.to" 
                  class="text-[#E8B86D]/40 hover:text-white transition-colors flex items-center gap-2.5 group/link text-sm"
                >
                  <span class="w-1 h-1 rounded-full bg-[#D9A05B] scale-0 group-hover/link:scale-100 transition-transform"></span>
                  <span class="font-light tracking-wide">{{ link.name }}</span>
                </RouterLink>
              </li>
            </ul>
          </div>
        </div>
      </div>

      <!-- Footer Bottom - Slimmer -->
      <div class="pt-6 border-t border-white/5 flex flex-col sm:flex-row justify-between items-center gap-6">
        <p class="text-[#E8B86D]/20 text-xs font-light">&copy; 2026 ትዕዛዝGo. All rights reserved.</p>
        
        <div class="flex items-center gap-6">
          <a href="#" class="text-[#E8B86D]/20 hover:text-[#D9A05B]/60 text-[10px] uppercase tracking-widest transition-colors">Privacy</a>
          <a href="#" class="text-[#E8B86D]/20 hover:text-[#D9A05B]/60 text-[10px] uppercase tracking-widest transition-colors">Terms</a>
          <div class="w-8 h-8 rounded-full bg-gradient-to-br from-[#D9A05B]/10 to-transparent p-[1px]">
            <div class="w-full h-full rounded-full bg-black flex items-center justify-center">
              <div class="w-1.5 h-1.5 rounded-full bg-[#D9A05B]/40 animate-pulse"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700&family=Syne:wght@700;800&display=swap');

.font-outfit {
  font-family: 'Outfit', sans-serif;
}

.font-syne {
  font-family: 'Syne', sans-serif;
}

.footer-premium {
  box-shadow: inset 0 10px 30px rgba(0,0,0,0.8);
}

.newsletter-card {
  transition: all 0.4s ease;
}

.newsletter-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at top right, rgba(217,160,91,0.03), transparent);
  pointer-events: none;
}

/* Micro-interactions */
footer a, footer button {
  transition: all 0.3s cubic-bezier(0.165, 0.84, 0.44, 1);
}
</style>

