<script setup lang="ts">
import Navbar from '../components/Navbar.vue'

const plans = [
  {
    name: 'Bistro Basic',
    price: 'Free',
    description: 'Perfect for small cafes and start-up bistros.',
    features: [
      'Digital QR Menu',
      'Basic Order Taking',
      'up to 5 Tables',
      'Daily Revenue Report',
      'Email Support'
    ],
    buttonText: 'Get Cooking',
    popular: false
  },
  {
    name: 'Fine Dining Pro',
    price: '$49',
    period: '/month',
    description: 'Professional tools for high-volume restaurants.',
    features: [
      'Advanced Table Management',
      'Kitchen Display System (KDS)',
      'Inventory Tracking',
      'CRM & Guest Profiles',
      'Staff Performance Analytics',
      'Priority 24/7 Support'
    ],
    buttonText: 'Level Up',
    popular: true
  },
  {
    name: 'Michelin Elite',
    price: '$129',
    period: '/month',
    description: 'The ultimate suite for gourmet establishments.',
    features: [
      'Multi-location Sync',
      'VVIP Reservation System',
      'AI Menu Optimization',
      'Full API Access',
      'Dedicated Account Manager',
      'Custom White-label App',
      'Advanced POS Integration'
    ],
    buttonText: 'Go Michelin',
    popular: false
  }
]
</script>

<template>
  <div class="pricing-page min-h-screen bg-[#0A0A0A] selection:bg-[#D9A05B] selection:text-black relative">
    <!-- Background Image with Overlay -->
    <div class="fixed inset-0 z-0">
      <img src="/C:/Users/tiegi/.gemini/antigravity/brain/d8f66ed3-9d28-4917-8101-140ce8738b00/gourmet_restaurant_background_1773300387743.png" class="w-full h-full object-cover opacity-80" alt="Restaurant Background" />
      <div class="absolute inset-0 bg-gradient-to-b from-[#0A0A0A] via-[#0A0A0A]/40 via-[#0A0A0A]/20 to-[#0A0A0A]"></div>
    </div>

    <Navbar />

    <!-- Hero Section -->
    <section class="pt-32 pb-20 px-6 relative z-10 overflow-hidden">
      <!-- Background Glows -->
      <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-full bg-[radial-gradient(circle_at_center,rgba(217,160,91,0.08)_0%,transparent_70%)] pointer-events-none"></div>
      
      <div class="container mx-auto text-center relative z-10">
        <h1 class="text-4xl md:text-6xl font-bold text-white mb-6 font-serif">
          The <span class="text-transparent bg-clip-text bg-gradient-to-r from-[#E8B86D] to-[#B8860B]">Recipe for Success</span>
        </h1>
        <p class="text-gray-400 text-lg max-w-2xl mx-auto mb-12">
          Elevate your establishment with our premium restaurant management solutions. Choose a plan that matches your ambition.
        </p>

        <!-- Pricing Grid -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-7xl mx-auto">
          <div 
            v-for="plan in plans" 
            :key="plan.name"
            :class="[
              'relative p-8 rounded-3xl border transition-all duration-500 flex flex-col backdrop-blur-sm',
              plan.popular 
                ? 'bg-[#15120b]/80 border-[#D9A05B] shadow-[0_0_50px_-12px_rgba(217,160,91,0.2)] scale-105 z-10' 
                : 'bg-[#111111]/80 border-white/5 hover:border-[#D9A05B]/30'
            ]"
          >
            <!-- Popular Badge -->
            <div v-if="plan.popular" class="absolute -top-4 left-1/2 -translate-x-1/2 bg-gradient-to-r from-[#E8B86D] to-[#B8860B] text-black text-[10px] font-bold px-4 py-1.5 rounded-full uppercase tracking-widest shadow-lg">
              Chef's Choice
            </div>

            <div class="mb-8 text-left">
              <h3 class="text-xl font-bold text-white mb-2">{{ plan.name }}</h3>
              <p class="text-gray-500 text-sm h-10 leading-relaxed">{{ plan.description }}</p>
            </div>

            <div class="mb-8 flex items-baseline gap-1">
              <span class="text-5xl font-bold text-white">{{ plan.price }}</span>
              <span v-if="plan.period" class="text-gray-500 text-sm">{{ plan.period }}</span>
            </div>

            <ul class="space-y-4 mb-10 flex-1 text-left">
              <li v-for="feature in plan.features" :key="feature" class="flex items-start gap-3 text-sm text-gray-300">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-[#D9A05B] shrink-0 mt-0.5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
                  <polyline points="20 6 9 17 4 12"></polyline>
                </svg>
                <span>{{ feature }}</span>
              </li>
            </ul>

            <button 
              :class="[
                'w-full py-4 rounded-xl font-bold transition-all duration-300 text-sm uppercase tracking-wider',
                plan.popular
                  ? 'bg-gradient-to-r from-[#E8B86D] via-[#D9A05B] to-[#C49245] text-black shadow-lg shadow-[#D9A05B]/20 hover:shadow-[#D9A05B]/40 transform hover:-translate-y-1'
                  : 'bg-white/5 text-white border border-white/10 hover:bg-white/10 hover:border-white/20'
              ]"
            >
              {{ plan.buttonText }}
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Preview -->
    <section class="py-20 bg-[#080808]/80 backdrop-blur-md border-t border-white/5 relative z-10">
      <div class="container mx-auto px-6 max-w-4xl text-center">
        <h2 class="text-3xl font-bold text-white mb-12 font-serif">Kitchen Queries</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6 text-left">
          <div class="p-6 rounded-2xl bg-white/[0.02] border border-white/5 hover:border-[#D9A05B]/20 transition-colors">
            <h4 class="text-white font-semibold mb-2 text-sm flex items-center gap-2">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 text-[#D9A05B]" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
              Can I change my plan as I grow?
            </h4>
            <p class="text-gray-500 text-xs leading-relaxed">Absolutely. Transition between Bistro and Michelin tiers seamlessly as your restaurant expands. Your data stays preserved.</p>
          </div>
          <div class="p-6 rounded-2xl bg-white/[0.02] border border-white/5 hover:border-[#D9A05B]/20 transition-colors">
            <h4 class="text-white font-semibold mb-2 text-sm flex items-center gap-2">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 text-[#D9A05B]" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c-1.657 0-3 .895-3 2s1.343 2 3 2 3 .895 3 2-1.343 2-3 2m0-8c1.11 0 2.08.402 2.599 1M12 8V7m0 1v8m0 0v1m0-1c-1.11 0-2.08-.402-2.599-1M21 12a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
              Are there hidden kitchen fees?
            </h4>
            <p class="text-gray-500 text-xs leading-relaxed">No. We believe in transparency. What you see on the menu is what you pay. No setup fees or surprise transaction cuts.</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Inter:wght@400;500;600;700&display=swap');

.pricing-page {
  font-family: 'Inter', sans-serif;
  scrollbar-width: thin;
  scrollbar-color: #D9A05B transparent;
}

.pricing-page .font-serif {
  font-family: 'Playfair Display', serif;
}

.pricing-page::-webkit-scrollbar {
  width: 6px;
}

.pricing-page::-webkit-scrollbar-thumb {
  background-color: #D9A05B;
  border-radius: 10px;
}
</style>
