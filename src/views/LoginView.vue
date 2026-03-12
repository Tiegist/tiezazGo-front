<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { useRouter } from 'vue-router'
import Navbar from '../components/Navbar.vue'

const router = useRouter()
const email = ref('admin@tizazgo.com')
const password = ref('patigo123')
const rememberMe = ref(false)
const isLoading = ref(false)
const errorMessage = ref('')

onMounted(() => {
  const savedEmail = localStorage.getItem('rememberedEmail')
  const savedPassword = localStorage.getItem('rememberedPassword')
  const savedRemember = localStorage.getItem('rememberMe') === 'true'

  if (savedRemember && savedEmail && savedPassword) {
    email.value = savedEmail
    password.value = savedPassword
    rememberMe.value = true
  }
})

const handleLogin = async () => {
  isLoading.value = true
  errorMessage.value = ''

  await new Promise((resolve) => setTimeout(resolve, 2000))

  if (email.value === 'admin@tizazgo.com' && password.value === 'patigo123') {
    if (rememberMe.value) {
      localStorage.setItem('rememberedEmail', email.value)
      localStorage.setItem('rememberedPassword', password.value)
      localStorage.setItem('rememberMe', 'true')
    } else {
      localStorage.removeItem('rememberedEmail')
      localStorage.removeItem('rememberedPassword')
      localStorage.removeItem('rememberMe')
    }
    router.push('/dashboard')
  } else {
    errorMessage.value = 'Invalid email or password. Please try again.'
  }

  isLoading.value = false
}
</script>

<template>
  <div class="login-page min-h-screen relative overflow-hidden selection:bg-[#E8B86D] selection:text-black bg-[#0A0A0A]">
    <Navbar />
    
    <!-- Background Layers (Simplified for split view) -->
    <div class="absolute inset-0 z-0">
      <div class="absolute inset-0 bg-gradient-to-br from-[#1a1710] via-[#0A0A0A] to-[#0A0A0A]"></div>
      <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_top_left,rgba(232,184,109,0.1)_0%,transparent_50%)]"></div>
    </div>

    <!-- Vertical Text -->
    <div class="fixed right-6 top-1/2 -translate-y-1/2 hidden xl:block z-10">
      <h2 class="text-[#D9A05B]/15 text-7xl font-bold rotate-90 origin-center tracking-[0.2em] whitespace-nowrap font-serif pointer-events-none">
        LOGIN
      </h2>
    </div>

    <!-- Main Content -->
    <div class="relative z-10 min-h-screen flex items-center justify-center pt-20 pb-8 px-4 md:px-8">
      <div class="w-full max-w-[1100px] overflow-hidden flex flex-col md:flex-row min-h-[650px]">

        <!-- Left Side: Food Image Panel -->
        <div class="md:w-[52%] relative hidden md:flex items-center justify-center overflow-hidden rounded-l-3xl bg-[#0c0a06]">
          <!-- Bright warm overlay -->
          <div class="absolute inset-0 bg-gradient-to-br from-[#241c0f]/80 via-[#16120a]/85 to-[#0c0a06]/90 z-[1]"></div>
          <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_center,rgba(232,184,109,0.18)_0%,transparent_65%)] z-[2]"></div>

          <!-- Bright golden halo -->
          <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[320px] h-[320px] rounded-full bg-[#D9A05B]/8 z-[3]"></div>
          <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[280px] h-[280px] rounded-full border-2 border-[#E8B86D]/15 z-[3]"></div>

          <!-- Particles -->
          <div class="absolute top-[12%] left-[18%] w-3 h-3 bg-[#E8B86D]/60 rounded-full blur-[2px] animate-bounce z-[4]"></div>
          <div class="absolute bottom-[18%] right-[18%] w-3.5 h-3.5 bg-[#F5D49A]/50 rounded-full blur-[2px] animate-pulse z-[4]"></div>

          <img
            src="/images/auth_burger.png"
            alt="Gourmet Burger"
            class="relative z-10 w-[82%] object-contain drop-shadow-[0_15px_40px_rgba(232,184,109,0.2)] hover:scale-105 transition-transform duration-700"
          />

          <!-- Branding Strip -->
          <div class="absolute bottom-0 left-0 right-0 z-20 px-8 py-6 bg-gradient-to-t from-black/70 via-black/30 to-transparent">
            <div class="flex items-center justify-between">
              <div>
                <p class="text-[#E8B86D] text-[10px] tracking-[0.35em] uppercase font-bold">Premium Quality</p>
                <p class="text-white/50 text-[11px] mt-1 font-light">Handcrafted with passion</p>
              </div>
              <div class="flex gap-1.5 items-center">
                <div class="w-1.5 h-1.5 rounded-full bg-[#D9A05B]/30"></div>
                <div class="w-6 h-1.5 rounded-full bg-gradient-to-r from-[#D9A05B] to-[#E8B86D]"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Right Side: Login Form -->
        <div class="md:w-[48%] relative">
          <!-- Premium glass card -->
          <div class="h-full bg-gradient-to-b from-[#1e1a10]/95 to-[#15120b]/95 backdrop-blur-2xl md:rounded-r-3xl rounded-3xl md:rounded-l-none p-8 sm:p-10 md:p-10 lg:p-12 flex flex-col justify-center border border-[#D9A05B]/20 shadow-[0_0_80px_-20px_rgba(232,184,109,0.15)]">

            <!-- Accents -->
            <div class="absolute top-0 left-[10%] right-[10%] h-[1px] bg-gradient-to-r from-transparent via-[#E8B86D]/40 to-transparent"></div>
            <div class="absolute top-4 right-4 w-6 h-6 border-t border-r border-[#D9A05B]/20 rounded-tr-lg"></div>

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
              <h1 class="text-3xl md:text-[2rem] font-bold text-white mb-2 font-serif leading-tight">Welcome Back</h1>
              <p class="text-[#E8B86D]/70 text-sm">Sign in to continue your journey</p>
            </div>

            <form @submit.prevent="handleLogin" class="space-y-5">
              <div>
                <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase mb-2">Email Address</label>
                <div class="relative group">
                  <div class="absolute left-4 top-1/2 -translate-y-1/2 text-[#D9A05B]/30 group-focus-within:text-[#D9A05B] transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="4" width="20" height="16" rx="3"/><polyline points="2 4 12 13 22 4"/></svg>
                  </div>
                  <input
                    v-model="email"
                    type="email"
                    placeholder="Enter your email"
                    class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-3.5 pl-12 pr-5 text-white text-[15px] focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 focus:bg-white/[0.05] transition-all"
                  />
                </div>
              </div>

              <div>
                <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase mb-2">Password</label>
                <div class="relative group">
                  <div class="absolute left-4 top-1/2 -translate-y-1/2 text-[#D9A05B]/30 group-focus-within:text-[#D9A05B] transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="11" width="18" height="11" rx="3"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
                  </div>
                  <input
                    v-model="password"
                    type="password"
                    placeholder="Enter password"
                    class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-3.5 pl-12 pr-5 text-white text-[15px] focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 focus:bg-white/[0.05] transition-all"
                  />
                </div>
              </div>

              <div v-if="errorMessage" class="bg-red-500/10 text-red-400 p-3 rounded-xl text-xs font-medium border border-red-500/20 flex items-center gap-2">
                {{ errorMessage }}
              </div>

              <div class="flex items-center justify-between">
                <label class="flex items-center gap-2 cursor-pointer group">
                  <input type="checkbox" v-model="rememberMe" class="w-3.5 h-3.5 rounded bg-white/5 border-white/10 text-[#D9A05B] focus:ring-[#D9A05B]" />
                  <span class="text-xs text-white/40 group-hover:text-white/60 transition-colors">Remember me</span>
                </label>
                <a href="#" class="text-xs text-[#E8B86D]/70 hover:text-[#E8B86D] transition-colors font-medium">Forgot?</a>
              </div>

              <button
                :disabled="isLoading"
                class="w-full bg-gradient-to-r from-[#E8B86D] via-[#D9A05B] to-[#C49245] text-black py-4 rounded-xl font-bold shadow-lg shadow-[#D9A05B]/10 hover:shadow-[#D9A05B]/30 hover:scale-[1.01] active:scale-[0.99] transition-all flex items-center justify-center gap-2 text-sm uppercase tracking-widest disabled:opacity-50"
              >
                <template v-if="isLoading">
                  <svg class="animate-spin h-5 w-5 text-black" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                    <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                    <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                  </svg>
                </template>
                <template v-else>
                  Sign In
                  <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
                </template>
              </button>
            </form>

            <p class="text-center mt-8 text-xs text-white/30">
              Don't have an account?
              <router-link to="/register" class="text-[#E8B86D] font-bold hover:text-[#F0C078] transition-colors ml-1">Join the Feast</router-link>
            </p>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@400;600;700&display=swap');

.login-page {
  font-family: 'Inter', sans-serif;
}

.login-page .font-serif {
  font-family: 'Playfair Display', serif;
}
</style>

