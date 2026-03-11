<script setup lang="ts">
import { ref } from 'vue'

const email = ref('')
const password = ref('')
const confirmPassword = ref('')
const agreeTerms = ref(false)
</script>

<template>
  <div class="min-h-screen bg-[#0A0A0A] flex items-center justify-center md:p-4 font-sans">
    <!-- Vertical Text indicator (left side for Sign Up) -->
    <div class="fixed left-4 top-1/2 -translate-y-1/2 hidden xl:block">
      <h2 class="text-white/20 text-6xl font-bold -rotate-90 origin-center tracking-widest whitespace-nowrap">
        Sign Up
      </h2>
    </div>

    <!-- Main Container -->
    <div class="w-full max-w-4xl bg-white md:rounded-[2rem] overflow-hidden flex flex-col md:flex-row shadow-2xl min-h-screen md:min-h-0">

      <!-- Left Side: Registration Form -->
      <div class="md:w-1/2 p-8 sm:p-10 md:p-12 flex flex-col justify-center -mt-6">
        <!-- Logo -->
        <div class="flex items-center gap-2 mb-8 justify-center md:justify-start">
          <div class="text-[#A31621] text-4xl font-bold flex items-center">
            <span class="text-5xl -mt-1">P</span>
            <span class="tracking-tighter">ringo</span>
            <span class="text-[#2C2C2C]">Es</span>
          </div>
        </div>

        <div class="mb-8 -mt-5 text-center md:text-left">
          <h1 class="text-2xl font-bold text-gray-800 mb-1">Sign up your account</h1>
          <p class="text-gray-400 text-sm">Welcome! Register with Email</p>
        </div>

        <form @submit.prevent class="space-y-4">
          <input
            v-model="email"
            type="text"
            placeholder="Number or email address"
            class="w-full bg-[#F5F7FA] border border-gray-100 rounded-xl py-4 px-5 text-gray-800 focus:outline-none focus:ring-2 focus:ring-[#A31621]/20 transition-all placeholder-gray-300 -mt-5"
          />

          <input
            v-model="password"
            type="password"
            placeholder="Password"
            class="w-full bg-[#F5F7FA] border border-gray-100 rounded-xl py-4 px-5 text-gray-800 focus:outline-none focus:ring-2 focus:ring-[#A31621]/20 transition-all placeholder-gray-300"
          />

          <input
            v-model="confirmPassword"
            type="password"
            placeholder="Confirm password"
            class="w-full bg-[#F5F7FA] border border-gray-100 rounded-xl py-4 px-5 text-gray-800 focus:outline-none focus:ring-2 focus:ring-[#A31621]/20 transition-all placeholder-gray-300"
          />

          <div class="flex items-center gap-2 py-2">
            <label class="flex items-center gap-2 cursor-pointer group">
              <input type="checkbox" v-model="agreeTerms" class="w-4 h-4 rounded text-[#A31621] border-gray-300 focus:ring-[#A31621]" />
              <span class="text-sm text-gray-400 group-hover:text-gray-600 transition-colors flex items-center gap-1">
                Agree
                <a href="#" class="text-[#2C2C2C] font-semibold hover:underline">terms & policy</a>
              </span>
            </label>
          </div>

          <button class="w-full bg-[#A31621] text-white py-4 rounded-xl font-bold shadow-lg shadow-[#A31621]/20 hover:bg-[#851219] transition-all transform hover:-translate-y-0.5 -mt-2">
            Sign Up
          </button>
        </form>

        <!-- Divider -->
        <div class="relative my-8 text-center mt-2">
          <div class="absolute inset-x-0 top-1/2 h-px bg-gray-100"></div>
          <span class="relative z-10 bg-white px-4 text-xs text-gray-300 font-medium">Or select method to sign up</span>
        </div>

        <!-- Social Logins -->
        <div class="grid grid-cols-2 gap-4 -mt-5">
          <button class="flex items-center justify-center gap-2 py-3 px-4 border border-gray-100 rounded-xl hover:bg-gray-50 transition-colors">
            <img src="https://www.svgrepo.com/show/475656/google-color.svg" class="w-5 h-5" alt="Google" />
            <span class="text-sm font-medium text-gray-600">Google</span>
          </button>
          <button class="flex items-center justify-center gap-2 py-3 px-4 border border-gray-100 rounded-xl hover:bg-gray-50 transition-colors">
            <img src="https://www.svgrepo.com/show/475647/facebook-color.svg" class="w-5 h-5" alt="Facebook" />
            <span class="text-sm font-medium text-gray-600">Facebook</span>
          </button>
        </div>

        <p class="text-center mt-1 text-sm text-gray-400 ">
          Do you have an account?
          <router-link to="/login" class="text-[#A31621] font-bold hover:underline">Login</router-link>
        </p>
      </div>

      <!-- Right Side: Image (Burger) -->
      <div class="md:w-1/2 bg-[#0A0A0A] relative hidden md:flex items-center justify-center overflow-hidden">
        <!-- Floating ingredients effect background (simulated) -->
        <div class="absolute inset-0 opacity-40">
           <div class="absolute top-20 right-20 w-4 h-4 bg-orange-500 rounded-full blur-sm animate-pulse"></div>
           <div class="absolute top-1/2 left-10 w-6 h-6 bg-yellow-500 rounded-full blur-md animate-bounce"></div>
        </div>

        <img src="/images/auth_burger.png" alt="Gourmet Burger" class="relative z-10 w-[90%] md:w-full object-contain transform scale-110 rotate-3 drop-shadow-[0_20px_50px_rgba(0,0,0,0.8)]" />

        <!-- Pagination dots like in the image -->
        <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex gap-2">
          <div class="w-2 h-2 rounded-full bg-white/20"></div>
          <div class="w-2 h-2 rounded-full bg-white/20"></div>
          <div class="w-5 h-2 rounded-full bg-white"></div>
        </div>
      </div>

    </div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');

.font-sans {
  font-family: 'Plus Jakarta Sans', sans-serif;
}
</style>
