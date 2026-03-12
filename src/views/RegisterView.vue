<script setup lang="ts">
import { ref } from 'vue'
import Navbar from '../components/Navbar.vue'

const email = ref('')
const password = ref('')
const confirmPassword = ref('')
const agreeTerms = ref(false)
</script>

<template>
  <div class="register-page min-h-screen relative overflow-hidden selection:bg-[#E8B86D] selection:text-black bg-[#0A0A0A]">
    <Navbar />

    <!-- Background Layers -->
    <div class="absolute inset-0 z-0">
      <div class="absolute inset-0 bg-gradient-to-bl from-[#1a1710] via-[#0A0A0A] to-[#0A0A0A]"></div>
      <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_top_right,rgba(232,184,109,0.15)_0%,transparent_50%)]"></div>
    </div>

    <!-- Vertical Text -->
    <div class="fixed left-6 top-1/2 -translate-y-1/2 hidden xl:block z-10">
      <h2 class="text-[#D9A05B]/15 text-7xl font-bold -rotate-90 origin-center tracking-[0.2em] whitespace-nowrap font-serif pointer-events-none">
        SIGN UP
      </h2>
    </div>

    <!-- Main Content -->
    <div class="relative z-10 min-h-screen flex items-center justify-center pt-20 pb-8 px-4 md:px-8">
      <div class="w-full max-w-[1100px] overflow-hidden flex flex-col md:flex-row min-h-[650px]">

        <!-- Left Side: Registration Form -->
        <div class="md:w-[48%] relative order-2 md:order-1">
          <!-- Premium glass card -->
          <div class="h-full bg-gradient-to-b from-[#1e1a10]/95 to-[#15120b]/95 backdrop-blur-2xl md:rounded-l-3xl rounded-3xl md:rounded-r-none p-8 sm:p-10 md:p-10 lg:p-12 flex flex-col justify-center border border-[#D9A05B]/20 shadow-[0_0_80px_-20px_rgba(232,184,109,0.15)]">

            <!-- Accents -->
            <div class="absolute top-0 left-[10%] right-[10%] h-[1px] bg-gradient-to-r from-transparent via-[#E8B86D]/40 to-transparent"></div>
            <div class="absolute bottom-4 right-4 w-6 h-6 border-b border-r border-[#D9A05B]/20 rounded-br-lg"></div>

            <!-- Logo -->
            <div class="flex items-center gap-3 mb-8 justify-center md:justify-start">
              <div class="w-10 h-10 bg-gradient-to-br from-[#E8B86D] to-[#B8860B] rounded-xl flex items-center justify-center shadow-lg shadow-[#D9A05B]/20">
                <span class="text-black font-bold text-sm">V</span>
              </div>
              <div>
                <span class="text-lg font-bold tracking-tight text-white block leading-none">VenobHD</span>
                <span class="text-[8px] text-[#D9A05B]/60 tracking-[0.2em] uppercase font-medium">Gourmet Tech</span>
              </div>
            </div>

            <div class="mb-7 text-center md:text-left">
              <h1 class="text-3xl md:text-[2rem] font-bold text-white mb-2 font-serif leading-tight">Join the Feast</h1>
              <p class="text-[#E8B86D]/70 text-sm">Create your account to start</p>
            </div>

            <form @submit.prevent class="space-y-4">
              <div>
                <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase mb-2">Email Address</label>
                <div class="relative group">
                  <div class="absolute left-4 top-1/2 -translate-y-1/2 text-[#D9A05B]/30 group-focus-within:text-[#D9A05B] transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                  </div>
                  <input
                    v-model="email"
                    type="text"
                    placeholder="Enter your email"
                    class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-3 pl-12 pr-5 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all"
                  />
                </div>
              </div>

              <div>
                <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase mb-2">Password</label>
                <input
                  v-model="password"
                  type="password"
                  placeholder="Create password"
                  class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-3 px-5 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all"
                />
              </div>

              <div>
                <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase mb-2">Confirm Password</label>
                <input
                  v-model="confirmPassword"
                  type="password"
                  placeholder="Re-enter password"
                  class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-3 px-5 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all"
                />
              </div>

              <div class="flex items-center gap-2 py-1">
                <label class="flex items-center gap-2.5 cursor-pointer group">
                  <input type="checkbox" v-model="agreeTerms" class="w-3.5 h-3.5 rounded bg-white/5 border-white/10 text-[#D9A05B] focus:ring-[#D9A05B]" />
                  <span class="text-xs text-white/40 group-hover:text-white/60 transition-colors">Agree to terms</span>
                </label>
              </div>

              <button class="w-full bg-gradient-to-r from-[#E8B86D] via-[#D9A05B] to-[#C49245] text-black py-4 rounded-xl font-bold shadow-lg hover:scale-[1.01] active:scale-[0.99] transition-all text-sm uppercase tracking-widest flex items-center justify-center gap-2">
                Create Account
                <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
              </button>
            </form>

            <p class="text-center mt-8 text-xs text-white/30">
              Already have an account?
              <router-link to="/login" class="text-[#E8B86D] font-bold hover:text-[#F0C078] transition-colors ml-1">Sign In</router-link>
            </p>
          </div>
        </div>

        <!-- Right Side: Food Image Panel -->
        <div class="md:w-[52%] relative hidden md:flex items-center justify-center overflow-hidden rounded-r-3xl bg-[#0c0a06] order-1 md:order-2">
          <div class="absolute inset-0 bg-gradient-to-bl from-[#241c0f]/80 via-[#16120a]/85 to-[#0c0a06]/90 z-[1]"></div>
          <img src="/images/auth_burger.png" alt="Gourmet Burger" class="relative z-10 w-[82%] object-contain transform rotate-3 drop-shadow-[0_15px_40px_rgba(232,184,109,0.2)]" />
          
          <div class="absolute bottom-0 left-0 right-0 z-20 px-8 py-6 bg-gradient-to-t from-black/70 to-transparent">
            <p class="text-[#E8B86D] text-[10px] tracking-[0.35em] uppercase font-bold">Artisan Crafted</p>
            <p class="text-white/40 text-[10px] mt-1">Only the finest ingredients</p>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@400;600;700&display=swap');

.register-page {
  font-family: 'Inter', sans-serif;
}

.register-page .font-serif {
  font-family: 'Playfair Display', serif;
}
</style>
