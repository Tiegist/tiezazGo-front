<script setup lang="ts">
import { ref } from 'vue'
import { RouterLink } from 'vue-router'

const isMobileMenuOpen = ref(false)
</script>

<template>
  <header class="fixed top-0 left-0 right-0 z-50 bg-black/20 backdrop-blur-md">
    <nav class="container mx-auto px-6 h-20 flex items-center justify-between">
      <RouterLink to="/" class="flex items-center gap-2 group cursor-pointer">
        <div class="w-8 h-8 bg-gradient-to-br from-[#D9A05B] to-[#B8860B] rounded-full flex items-center justify-center">
          <span class="text-black font-bold text-xs">V</span>
        </div>
        <span class="text-xl font-bold tracking-tight text-white group-hover:text-[#D9A05B] transition-colors">VenobHD</span>
      </RouterLink>

      <!-- Desktop Nav -->
      <ul class="hidden lg:flex items-center gap-8 text-sm font-medium text-gray-300">
        <li><RouterLink to="/" class="hover:text-[#D9A05B] transition-colors">Home</RouterLink></li>
        <li><a href="#" class="hover:text-[#D9A05B] transition-colors relative after:absolute after:bottom-[-4px] after:left-0 after:w-full after:h-[2px] after:bg-[#D9A05B]">Packages</a></li>
        <li><a href="#" class="hover:text-[#D9A05B] transition-colors">Pizza</a></li>
        <li><a href="#" class="hover:text-[#D9A05B] transition-colors">Burger</a></li>
        <li><a href="#" class="hover:text-[#D9A05B] transition-colors">Contact</a></li>
        <li>
          <RouterLink to="/login" class="hover:text-[#D9A05B] transition-colors flex items-center gap-1">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
              <circle cx="12" cy="7" r="4"></circle>
            </svg>
            Sign In
          </RouterLink>
        </li>
      </ul>

      <button class="hidden lg:block bg-gradient-to-r from-[#D9A05B] to-[#B8860B] text-black px-6 py-2.5 rounded-full text-sm font-bold shadow-lg shadow-orange-900/20 hover:scale-105 transition-transform">
        Contact Details
      </button>

      <!-- Mobile Menu Toggle -->
      <button @click="isMobileMenuOpen = !isMobileMenuOpen" class="lg:hidden text-white p-2">
        <svg v-if="!isMobileMenuOpen" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
        </svg>
        <svg v-else xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
      </button>
    </nav>

    <!-- Mobile Navigation Drawer -->
    <transition
      enter-active-class="transform transition ease-in-out duration-300"
      enter-from-class="-translate-y-full"
      enter-to-class="translate-y-0"
      leave-active-class="transform transition ease-in-out duration-300"
      leave-from-class="translate-y-0"
      leave-to-class="-translate-y-full"
    >
      <div v-if="isMobileMenuOpen" class="lg:hidden bg-black/95 absolute top-20 left-0 right-0 py-8 px-6 border-b border-white/10 shadow-2xl backdrop-blur-xl">
        <ul class="flex flex-col items-center gap-6 text-lg font-medium">
          <li><RouterLink to="/" @click="isMobileMenuOpen = false" class="text-[#D9A05B]">Home</RouterLink></li>
          <li><a href="#" @click="isMobileMenuOpen = false" class="hover:text-[#D9A05B] transition-colors text-white">Packages</a></li>
          <li><a href="#" @click="isMobileMenuOpen = false" class="hover:text-[#D9A05B] transition-colors text-white">Pizza</a></li>
          <li><a href="#" @click="isMobileMenuOpen = false" class="hover:text-[#D9A05B] transition-colors text-white">Burger</a></li>
          <li><a href="#" @click="isMobileMenuOpen = false" class="hover:text-[#D9A05B] transition-colors text-white">Contact</a></li>
          <li><RouterLink to="/login" @click="isMobileMenuOpen = false" class="hover:text-[#D9A05B] transition-colors text-white">Sign In</RouterLink></li>
          <li class="w-full pt-4 border-t border-white/10">
            <button class="w-full bg-gradient-to-r from-[#D9A05B] to-[#B8860B] text-black px-6 py-3 rounded-full font-bold">
              Contact Details
            </button>
          </li>
        </ul>
      </div>
    </transition>
  </header>
</template>
