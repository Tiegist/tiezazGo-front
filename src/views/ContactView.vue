<script setup lang="ts">
import { ref } from 'vue'
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'
import contactBg from '../assets/contact-bg.png'

const formData = ref({
  fullName: '',
  email: '',
  phone: '',
  company: '',
  subject: '',
  message: ''
})

const subjects = [
  'General Inquiry',
  'Sales & Pricing',
  'Technical Support',
  'Partnership Opportunities',
  'Other'
]

const contactCards = [
  {
    icon: 'M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z',
    title: 'Email Support',
    description: 'Our team is here to help you with any technical or general questions.',
    value: 'support@tiezazgo.com'
  },
  {
    icon: 'M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 7V5z',
    title: 'Phone',
    description: 'Call us directly for immediate assistance during business hours.',
    value: '+1 (555) 000-0000'
  },
  {
    icon: 'M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z M15 11a3 3 0 11-6 0 3 3 0 016 0z',
    title: 'Office Location',
    description: 'Visit our headquarters for a coffee and a chat about your project.',
    value: '123 Gourmet Ave, Tech City, TC 54321'
  },
  {
    icon: 'M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z',
    title: 'Business Hours',
    description: 'We are available to serve you during these hours.',
    value: 'Mon - Fri: 9:00 AM - 6:00 PM'
  }
]

const faqs = ref([
  {
    question: 'How does the QR menu system work?',
    answer: 'Once you upload your menu, we generate a unique QR code for each table. Customers scan the code with their phones to view the menu and place orders directly to your kitchen.',
    isOpen: false
  },
  {
    question: 'How long does setup take?',
    answer: 'Basic setup can be completed in under 30 minutes. Full customization for multiple branches usually takes 1-2 business days with our white-glove onboarding.',
    isOpen: false
  },
  {
    question: 'Can cafés customize their menus?',
    answer: 'Absolutely! Our system offers full control over branding, colors, high-quality food photography, and real-time availability updates.',
    isOpen: false
  }
])

const toggleFaq = (index: number) => {
  if (faqs.value[index]) {
    faqs.value[index].isOpen = !faqs.value[index].isOpen
  }
}

const handleSubmit = () => {
  console.log('Form submitted:', formData.value)
  // Logic for form submission would go here
}
</script>

<template>
  <div class="contact-page min-h-screen bg-[#0A0A0A] selection:bg-[#D9A05B] selection:text-black relative overflow-x-hidden">
    <!-- Background Elements -->
    <div class="fixed inset-0 z-0">
      <div class="absolute inset-0 bg-gradient-to-b from-[#1a1710] via-[#0A0A0A] to-[#0A0A0A]"></div>
      <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-[600px] bg-[radial-gradient(circle_at_center,rgba(217,160,91,0.08)_0%,transparent_70%)] pointer-events-none"></div>
    </div>

    <Navbar />

    <section class="relative pt-48 pb-32 px-6 overflow-hidden">
      <!-- Image Background - Ultra Visibility -->
      <div class="absolute inset-0 z-0">
        <img :src="contactBg" alt="" class="w-full h-full object-cover opacity-100 brightness-110" />
        <div class="absolute inset-0 bg-gradient-to-b from-transparent via-transparent to-[#0A0A0A]"></div>
      </div>

      <div class="container mx-auto max-w-4xl relative z-10 text-center">
        <!-- Glassmorphism content card -->
        <div class="inline-block px-10 py-12 rounded-[2.5rem] bg-black/30 backdrop-blur-md border border-white/10 shadow-2xl">
          <h1 class="text-5xl md:text-7xl font-serif text-white mb-6 drop-shadow-2xl">
            Contact <span class="bg-gradient-to-r from-[#D9A05B] to-[#FFE4AD] bg-clip-text text-transparent">Us</span>
          </h1>
          <p class="text-xl md:text-2xl text-white/90 max-w-2xl mx-auto font-light leading-relaxed drop-shadow-lg">
            Have questions about our QR menu system? Our team is here to help you elevate your dining experience.
          </p>
        </div>
      </div>
    </section>

    <!-- Info Cards Section -->
    <section class="py-12 px-6 relative z-10">
      <div class="container mx-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 max-w-7xl mx-auto">
          <div 
            v-for="card in contactCards" 
            :key="card.title"
            class="group p-8 rounded-3xl bg-[#111111]/80 border border-white/5 hover:border-[#D9A05B]/30 backdrop-blur-sm transition-all duration-500 hover:-translate-y-2 hover:shadow-[0_20px_40px_-15px_rgba(217,160,91,0.1)]"
          >
            <div class="w-12 h-12 bg-[#D9A05B]/10 rounded-xl flex items-center justify-center mb-6 group-hover:bg-[#D9A05B] transition-colors duration-500">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#D9A05B] group-hover:text-black transition-colors duration-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" :d="card.icon" />
              </svg>
            </div>
            <h3 class="text-lg font-bold text-white mb-3">{{ card.title }}</h3>
            <p class="text-gray-500 text-sm mb-4 leading-relaxed">{{ card.description }}</p>
            <p class="text-[#D9A05B] font-medium text-sm">{{ card.value }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Map and Form Section -->
    <section class="py-16 px-6 relative z-10">
      <div class="container mx-auto max-w-7xl">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-start">
          
          <!-- Contact Form -->
          <div class="bg-[#111111]/80 backdrop-blur-xl p-8 md:p-10 rounded-3xl border border-white/5 order-2 lg:order-1">
            <div class="absolute top-0 left-[10%] right-[10%] h-[1px] bg-gradient-to-r from-transparent via-[#E8B86D]/40 to-transparent"></div>
            
            <h2 class="text-2xl font-bold text-white mb-6 font-serif">Send a Message</h2>
            
            <form @submit.prevent="handleSubmit" class="space-y-6">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div class="space-y-2">
                  <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase">Full Name</label>
                  <input 
                    v-model="formData.fullName"
                    type="text" 
                    placeholder="John Doe"
                    class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-4 px-6 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all placeholder:text-white/10"
                  />
                </div>
                <div class="space-y-2">
                  <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase">Email Address</label>
                  <input 
                    v-model="formData.email"
                    type="email" 
                    placeholder="john@example.com"
                    class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-4 px-6 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all placeholder:text-white/10"
                  />
                </div>
              </div>

              <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <div class="space-y-2">
                  <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase">Phone Number</label>
                  <input 
                    v-model="formData.phone"
                    type="tel" 
                    placeholder="+1 (555) 000-0000"
                    class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-4 px-6 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all placeholder:text-white/10"
                  />
                </div>
                <div class="space-y-2">
                  <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase">Café / Company</label>
                  <input 
                    v-model="formData.company"
                    type="text" 
                    placeholder="Gourmet Café"
                    class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-4 px-6 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all placeholder:text-white/10"
                  />
                </div>
              </div>

              <div class="space-y-2">
                <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase">Subject</label>
                <select 
                  v-model="formData.subject"
                  class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-4 px-6 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all appearance-none cursor-pointer"
                >
                  <option value="" disabled selected class="bg-[#0A0A0A]">Select a subject</option>
                  <option v-for="subj in subjects" :key="subj" :value="subj" class="bg-[#0A0A0A]">{{ subj }}</option>
                </select>
              </div>

              <div class="space-y-2">
                <label class="block text-[10px] text-[#E8B86D] font-bold tracking-[0.2em] uppercase">Message</label>
                <textarea 
                  v-model="formData.message"
                  rows="4" 
                  placeholder="Tell us about your needs..."
                  class="w-full bg-white/[0.03] border border-white/10 rounded-xl py-4 px-6 text-white text-sm focus:outline-none focus:ring-1 focus:ring-[#E8B86D]/40 transition-all placeholder:text-white/10 resize-none"
                ></textarea>
              </div>

              <button class="w-full bg-gradient-to-r from-[#E8B86D] via-[#D9A05B] to-[#C49245] text-black py-5 rounded-xl font-bold shadow-lg hover:shadow-[#D9A05B]/20 transform hover:-translate-y-1 active:translate-y-0 transition-all text-sm uppercase tracking-widest flex items-center justify-center gap-3">
                Send Message
                <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5">
                  <path d="M22 2L11 13M22 2L15 22L11 13M11 13L2 9L22 2"/>
                </svg>
              </button>
            </form>
          </div>

          <!-- Map Section -->
          <div class="h-full space-y-8">
             <div class="w-full h-[500px] bg-[#111111] rounded-[2.5rem] border border-white/5 overflow-hidden relative shadow-2xl">
                <!-- Mock Map Illustration -->
                <div class="absolute inset-0 grayscale opacity-40">
                  <div class="w-full h-full bg-[radial-gradient(#333_1px,transparent_1px)] [background-size:20px_20px]"></div>
                </div>
                <!-- Interactive Pins Overlay -->
                <div class="absolute inset-0 flex items-center justify-center">
                   <div class="relative">
                      <div class="absolute inset-0 animate-ping rounded-full h-12 w-12 bg-[#D9A05B]/40"></div>
                      <div class="relative bg-[#D9A05B] rounded-full h-12 w-12 flex items-center justify-center shadow-[0_0_30px_rgba(217,160,91,0.5)]">
                         <div class="bg-black rounded-full h-3 w-3"></div>
                      </div>
                   </div>
                </div>
                <!-- Location Label -->
                <div class="absolute bottom-8 left-8 right-8 bg-[#15120b]/90 backdrop-blur-xl border border-white/10 p-6 rounded-2xl flex items-center justify-between">
                   <div>
                      <h4 class="text-white font-bold text-sm">Main Office</h4>
                      <p class="text-gray-500 text-xs">Tech City, Innovation District</p>
                   </div>
                   <button class="text-[#D9A05B] text-xs font-bold uppercase tracking-widest hover:underline">Get Directions</button>
                </div>
                
                <!-- Overlay Gradient -->
                <div class="absolute inset-0 pointer-events-none bg-gradient-to-t from-black/60 to-transparent"></div>
             </div>

             <!-- Mini FAQ Card -->
             <div class="bg-white/[0.02] border border-white/5 rounded-3xl p-8 backdrop-blur-sm">
                <h3 class="text-white font-bold mb-6 text-lg">Quick Contact</h3>
                <div class="flex items-center gap-4 mb-4">
                   <div class="w-10 h-10 rounded-full bg-[#E8B86D]/10 flex items-center justify-center">
                      <span class="text-[#E8B86D] text-sm">⚡</span>
                   </div>
                   <div>
                      <p class="text-gray-400 text-xs mb-0.5">Response Time</p>
                      <p class="text-white text-sm font-semibold">Under 2 hours</p>
                   </div>
                </div>
             </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Full FAQ Section -->
    <section class="py-16 px-6 relative z-10 border-t border-white/5">
      <div class="container mx-auto max-w-4xl">
        <div class="text-center mb-12">
          <h2 class="text-3xl md:text-4xl font-bold text-white mb-4 font-serif">Frequently Asked Questions</h2>
          <p class="text-gray-500">Everything you need to know about our QR menu system.</p>
        </div>

        <div class="space-y-4">
          <div 
            v-for="(faq, index) in faqs" 
            :key="index"
            class="border border-white/5 rounded-2xl overflow-hidden bg-white/[0.01] hover:bg-white/[0.03] transition-all"
          >
            <button 
              @click="toggleFaq(index)"
              class="w-full p-6 flex items-center justify-between text-left focus:outline-none"
            >
              <span class="text-white font-semibold">{{ faq.question }}</span>
              <svg 
                xmlns="http://www.w3.org/2000/svg" 
                class="w-5 h-5 text-[#D9A05B] transition-transform duration-300"
                :class="{'rotate-180': faq.isOpen}"
                fill="none" viewBox="0 0 24 24" stroke="currentColor"
              >
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
              </svg>
            </button>
            <div 
              v-show="faq.isOpen"
              class="px-6 pb-6 text-gray-400 text-sm leading-relaxed"
            >
              {{ faq.answer }}
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-16 pb-24 px-6 relative z-10">
      <div class="container mx-auto max-w-5xl">
        <div class="relative p-12 md:p-20 rounded-[3rem] overflow-hidden text-center bg-gradient-to-br from-[#1e1a10] to-[#0A0A0A] border border-[#D9A05B]/30 shadow-2xl">
          <!-- Decorative Glow -->
          <div class="absolute -top-24 -right-24 w-64 h-64 bg-[#D9A05B]/10 blur-[80px] rounded-full"></div>
          <div class="absolute -bottom-24 -left-24 w-64 h-64 bg-[#D9A05B]/10 blur-[80px] rounded-full"></div>
          
          <div class="relative z-10">
            <h2 class="text-3xl md:text-5xl font-bold text-white mb-8 font-serif">Ready to bring 𝕿ዕዛዝ𝕲𝖔<br class="hidden md:block" /> to your café?</h2>
            
            <div class="flex flex-col sm:flex-row items-center justify-center gap-6 mt-12">
              <button class="w-full sm:w-auto px-10 py-5 bg-gradient-to-r from-[#E8B86D] via-[#D9A05B] to-[#C49245] text-black rounded-xl font-extrabold shadow-xl hover:scale-105 transition-all uppercase tracking-widest text-sm">
                Get Started
              </button>
              <button class="w-full sm:w-auto px-10 py-5 bg-white/5 text-white border border-white/10 rounded-xl font-bold hover:bg-white/10 transition-all uppercase tracking-widest text-sm">
                Book Demo
              </button>
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
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Inter:wght@400;500;600;700&display=swap');

.contact-page {
  font-family: 'Inter', sans-serif;
  scrollbar-width: thin;
  scrollbar-color: #D9A05B transparent;
}

.contact-page .font-serif {
  font-family: 'Playfair Display', serif;
}

.contact-page::-webkit-scrollbar {
  width: 6px;
}

.contact-page::-webkit-scrollbar-thumb {
  background-color: #D9A05B;
  border-radius: 10px;
}

/* Custom styles for select appearance */
select {
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 24 24' stroke='%23D9A05B'%3E%3Cpath stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='M19 9l-7 7-7-7'%3E%3C/path%3E%3C/svg%3E");
  background-position: right 1.5rem center;
  background-repeat: no-repeat;
  background-size: 1.25rem;
}

input:focus, select:focus, textarea:focus {
  background-color: rgba(255, 255, 255, 0.05);
}

.animate-ping {
  animation: ping 2s cubic-bezier(0, 0, 0.2, 1) infinite;
}

@keyframes ping {
  75%, 100% {
    transform: scale(2);
    opacity: 0;
  }
}
</style>
