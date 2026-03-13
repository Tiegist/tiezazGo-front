<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue'
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'

// --- Mock Data ---
const restaurantInfo = {
  name: 'Aroma Café',
  description: 'Fresh coffee, delicious meals, and cozy vibes.',
  motto: 'Brewing happiness, one cup at a time.',
  location: 'Addis Ababa, Ethiopia',
  rating: 4.7,
  reviews: 320,
  phone: '+251 911 234 567',
  status: 'Open',
  hours: '08:00 AM - 10:00 PM',
  logo: 'https://images.unsplash.com/photo-1554118811-1e0d58224f24?auto=format&fit=crop&q=80&w=200&h=200',
  banner: 'https://images.unsplash.com/photo-1501339847302-ac426a4a7cbb?auto=format&fit=crop&q=80&w=1600&h=600'
}

const categories = [
  'All', 'Breakfast', 'Coffee', 'Hot Drinks', 'Cold Drinks', 'Sandwiches', 'Burgers', 'Desserts', 'Special Offers', 'Weekend Special'
]

const menuItems = ref([
  {
    id: 1,
    name: 'Cappuccino',
    description: 'Rich espresso with steamed milk foam',
    price: 120,
    category: 'Coffee',
    rating: 4.8,
    tag: 'Popular',
    image: 'https://images.unsplash.com/photo-1572442388796-11668a67e53d?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 2,
    name: 'Cheese Burger',
    description: 'Juicy beef patty with melted cheese and fresh greens',
    price: 280,
    category: 'Burgers',
    rating: 4.9,
    tag: 'New',
    image: 'https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 3,
    name: 'Club Sandwich',
    description: 'Triple-decker with chicken, lettuce, tomato, and mayo',
    price: 220,
    category: 'Sandwiches',
    rating: 4.7,
    image: 'https://images.unsplash.com/photo-1528735602780-2552fd46c7af?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 4,
    name: 'Chocolate Cake',
    description: 'Decadent soft chocolate sponge with rich cream layers',
    price: 150,
    category: 'Desserts',
    rating: 4.9,
    tag: 'Popular',
    image: 'https://images.unsplash.com/photo-1578985545062-69928b1d9587?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 5,
    name: 'Latte',
    description: 'Smooth espresso with plenty of silky steamed milk',
    price: 110,
    category: 'Coffee',
    rating: 4.6,
    image: 'https://images.unsplash.com/photo-1593967858208-67ddb5b4cdeb?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 6,
    name: 'Chicken Burger',
    description: 'Crispy chicken breast with spicy mayo and slaw',
    price: 260,
    category: 'Burgers',
    rating: 4.8,
    tag: 'Popular',
    image: 'https://images.unsplash.com/photo-1625813506062-0aeb1d7a094b?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 7,
    name: 'Eggs Benedict',
    description: 'Poached eggs with hollandaise sauce on English muffins',
    price: 210,
    category: 'Breakfast',
    rating: 4.7,
    image: 'https://images.unsplash.com/photo-1600335895229-6e75511892c8?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 8,
    name: 'Pancakes',
    description: 'Fluffy pancakes with maple syrup and fresh berries',
    price: 180,
    category: 'Breakfast',
    rating: 4.6,
    image: 'https://images.unsplash.com/photo-1567620905732-2d1ec7bb7445?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 9,
    name: 'Green Tea',
    description: 'Steamed premium green tea leaves',
    price: 90,
    category: 'Hot Drinks',
    rating: 4.5,
    image: 'https://images.unsplash.com/photo-1627435601361-ec25f5b1d0e5?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 10,
    name: 'Hot Cocoa',
    description: 'Creamy milk chocolate with marshmallows',
    price: 130,
    category: 'Hot Drinks',
    rating: 4.8,
    image: 'https://images.unsplash.com/photo-1544787210-2211d4036504?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 11,
    name: 'Iced Latte',
    description: 'Espresso over ice with chilled milk',
    price: 125,
    category: 'Cold Drinks',
    rating: 4.7,
    image: 'https://images.unsplash.com/photo-1517701604599-bb22b5850422?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 12,
    name: 'Orange Juice',
    description: 'Freshly squeezed sun-ripened oranges',
    price: 110,
    category: 'Cold Drinks',
    rating: 4.9,
    image: 'https://images.unsplash.com/photo-1557800636-894a64c1696f?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 13,
    name: 'Lunch Special',
    description: 'Any burger with a cold drink and small fries',
    price: 420,
    category: 'Special Offers',
    rating: 4.8,
    tag: 'Deal',
    image: 'https://images.unsplash.com/photo-1594212699903-ec8a3eca50f5?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 14,
    name: 'Ethiopian Breakfast (Ful)',
    description: 'Traditional fava bean stew with spices, eggs, and bread',
    price: 230,
    category: 'Weekend Special',
    rating: 4.9,
    tag: 'Special',
    image: 'https://plus.unsplash.com/premium_photo-1663853051670-369403f0012f?auto=format&fit=crop&q=80&w=400&h=400'
  },
  {
    id: 15,
    name: 'Lamb Roast',
    description: 'Slow-cooked succulent lamb with rosemary and honey-glazed carrots',
    price: 580,
    category: 'Weekend Special',
    rating: 4.9,
    tag: 'Limited',
    image: 'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&q=80&w=400&h=400'
  }
])

// --- State Management ---
const activeCategory = ref('All')
const searchQuery = ref('')
const selectedItem = ref<any>(null)
const isItemModalOpen = ref(false)
const isCartOpen = ref(false)
const cart = ref<any[]>([])
const isScrolled = ref(false)

// --- Computed ---
const filteredItems = computed(() => {
  return menuItems.value.filter(item => {
    const matchesCategory = activeCategory.value === 'All' || item.category === activeCategory.value
    const matchesSearch = item.name.toLowerCase().includes(searchQuery.value.toLowerCase()) ||
                        item.description.toLowerCase().includes(searchQuery.value.toLowerCase())
    return matchesCategory && matchesSearch
  })
})

const cartTotal = computed(() => {
  return cart.value.reduce((total, item) => total + (item.price * item.quantity), 0)
})

const cartCount = computed(() => {
  return cart.value.reduce((count, item) => count + item.quantity, 0)
})

// --- Methods ---
const handleScroll = () => {
  isScrolled.value = window.scrollY > 300
}

const scrollToCategory = (category: string) => {
  activeCategory.value = category
  // In a real app, we might scroll to a ref
}

const openItemDetail = (item: any) => {
  selectedItem.value = { ...item, quantity: 1 }
  isItemModalOpen.value = true
}

const addToCart = (item: any) => {
  const existing = cart.value.find(i => i.id === item.id)
  if (existing) {
    existing.quantity += item.quantity || 1
  } else {
    cart.value.push({ ...item, quantity: item.quantity || 1 })
  }
  isItemModalOpen.value = false
}

const updateCartQuantity = (itemId: number, delta: number) => {
  const index = cart.value.findIndex(i => i.id === itemId)
  if (index !== -1) {
    cart.value[index].quantity += delta
    if (cart.value[index].quantity <= 0) {
      cart.value.splice(index, 1)
    }
  }
}

// --- Lifecycle ---
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <div class="min-h-screen bg-[#0A0A0A] text-white font-sans selection:bg-[#D9A05B]/30">
    <Navbar />

    <!-- 1. Restaurant Header Section -->
    <header class="relative h-[40vh] md:h-[50vh] overflow-hidden">
      <!-- Banner Image -->
      <img :src="restaurantInfo.banner" alt="Banner" class="w-full h-full object-cover scale-105" />
      <!-- Overlays -->
      <div class="absolute inset-0 bg-gradient-to-t from-[#0A0A0A] via-[#0A0A0A]/40 to-transparent"></div>
      <div class="absolute inset-0 bg-black/20"></div>

      <!-- Identity -->
      <div class="absolute bottom-0 left-0 w-full p-6 md:p-12">
        <div class="container mx-auto flex flex-col md:flex-row items-end gap-6">
          <!-- Logo -->
          <div class="relative group">
            <div class="absolute -inset-1 bg-gradient-to-r from-[#D9A05B] to-[#FFE4AD] rounded-2xl blur opacity-25 group-hover:opacity-50 transition duration-1000"></div>
            <img :src="restaurantInfo.logo" alt="Logo" class="relative w-24 h-24 md:w-32 md:h-32 rounded-2xl object-cover border-2 border-white/10 shadow-2xl" />
          </div>
          <!-- Info -->
          <div class="flex-1 pb-2">
            <div class="flex items-center gap-3 mb-2">
              <span class="px-3 py-1 bg-[#D9A05B] text-black text-[10px] font-bold rounded-full uppercase tracking-wider">
                {{ restaurantInfo.status }}
              </span>
              <div class="flex items-center text-[#D9A05B] text-sm">
                <span class="mr-1">⭐</span>
                <span class="font-bold">{{ restaurantInfo.rating }}</span>
                <span class="text-white/40 ml-1">({{ restaurantInfo.reviews }} reviews)</span>
              </div>
            </div>
            <h1 class="text-4xl md:text-6xl font-serif font-bold text-white mb-2 drop-shadow-xl">{{ restaurantInfo.name }}</h1>
            <p class="text-white/70 text-lg max-w-xl italic">{{ restaurantInfo.description }}</p>
          </div>
        </div>
      </div>
    </header>

    <!-- 2. & 3. Category Nav & Search (Sticky Container) -->
    <div :class="['sticky top-0 z-40 transition-all duration-300 border-b', isScrolled ? 'bg-[#111111]/95 backdrop-blur-xl border-white/5 py-4' : 'bg-transparent border-transparent py-6']">
      <div class="container mx-auto px-6">
        <div class="flex flex-col md:flex-row md:items-center justify-between gap-6">
          <!-- Horizontal Scrollable Categories -->
          <div class="flex items-center gap-2 overflow-x-auto no-scrollbar -mx-6 px-6 md:mx-0 md:px-0">
            <button 
              v-for="cat in categories" 
              :key="cat"
              @click="scrollToCategory(cat)"
              :class="[
                'whitespace-nowrap px-6 py-2.5 rounded-full text-sm font-medium transition-all duration-300 border',
                activeCategory === cat 
                  ? 'bg-[#D9A05B] text-black border-[#D9A05B] shadow-[0_4px_15px_rgba(217,160,91,0.3)]' 
                  : 'bg-white/5 text-white/60 border-white/5 hover:border-white/20 hover:text-white'
              ]"
            >
              {{ cat }}
            </button>
          </div>

          <!-- Search Bar -->
          <div class="relative min-w-[300px]">
            <input 
              v-model="searchQuery"
              type="text" 
              placeholder="Search dishes..."
              class="w-full bg-white/5 border border-white/10 rounded-2xl px-12 py-3 text-sm focus:outline-none focus:border-[#D9A05B]/50 transition-all placeholder:text-white/20"
            />
            <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 absolute left-4 top-1/2 -translate-y-1/2 text-white/40" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
            </svg>
          </div>
        </div>
      </div>
    </div>

    <main class="container mx-auto px-6 py-12">
      <!-- 5. Featured Section -->
      <section v-if="activeCategory === 'All' && !searchQuery" class="mb-16">
        <div class="flex items-center justify-between mb-8">
          <h2 class="text-3xl font-serif font-bold text-white">Most Popular</h2>
          <div class="h-[1px] flex-1 mx-8 bg-gradient-to-r from-white/5 via-white/10 to-transparent"></div>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div 
            v-for="item in menuItems.filter(i => i.tag === 'Popular').slice(0, 3)" 
            :key="'featured-' + item.id"
            class="group relative h-64 rounded-3xl overflow-hidden cursor-pointer shadow-2xl"
            @click="openItemDetail(item)"
          >
            <img :src="item.image" :alt="item.name" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" />
            <div class="absolute inset-0 bg-gradient-to-t from-black via-black/20 to-transparent opacity-80"></div>
            <div class="absolute bottom-0 left-0 p-8">
              <span class="px-3 py-1 bg-white/10 backdrop-blur-md text-[#D9A05B] text-[10px] font-bold rounded-full uppercase tracking-widest mb-3 inline-block">Featured</span>
              <h3 class="text-2xl font-bold text-white mb-1">{{ item.name }}</h3>
              <p class="text-[#D9A05B] font-bold">{{ item.price }} ETB</p>
            </div>
          </div>
        </div>
      </section>

      <!-- 4. Menu Item Grid -->
      <section>
        <div class="flex items-center justify-between mb-10">
          <h2 class="text-3xl font-serif font-bold text-white">
            {{ activeCategory === 'All' ? 'Full Menu' : activeCategory }}
          </h2>
          <span class="text-white/30 text-sm font-light">{{ filteredItems.length }} items available</span>
        </div>

        <div v-if="filteredItems.length" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
          <div 
            v-for="item in filteredItems" 
            :key="item.id"
            class="group bg-[#111111]/60 border border-white/5 rounded-3xl overflow-hidden hover:border-[#D9A05B]/30 hover:bg-[#161616] transition-all duration-500 cursor-pointer flex flex-col"
            @click="openItemDetail(item)"
          >
            <div class="relative h-48 overflow-hidden">
              <img :src="item.image" :alt="item.name" class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700" />
              <div v-if="item.tag" class="absolute top-4 right-4 px-3 py-1 bg-[#D9A05B] text-black text-[10px] font-bold rounded-full uppercase tracking-tighter">
                {{ item.tag }}
              </div>
            </div>
            <div class="p-6 flex-1 flex flex-col">
              <div class="flex justify-between items-start mb-2">
                <h3 class="text-lg font-bold text-white group-hover:text-[#D9A05B] transition-colors">{{ item.name }}</h3>
                <div class="flex items-center text-xs text-[#D9A05B]">
                  ⭐ {{ item.rating }}
                </div>
              </div>
              <p class="text-gray-500 text-sm line-clamp-2 mb-4 leading-relaxed">{{ item.description }}</p>
              <div class="mt-auto flex items-center justify-between pt-4 border-t border-white/5">
                <span class="text-lg font-bold text-white font-mono">{{ item.price }} ETB</span>
                <button 
                  @click.stop="addToCart(item)"
                  class="w-10 h-10 bg-white/5 hover:bg-[#D9A05B] hover:text-black rounded-full flex items-center justify-center transition-all duration-300"
                >
                  <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
                  </svg>
                </button>
              </div>
            </div>
          </div>
        </div>

        <!-- 404 Search State -->
        <div v-else class="py-20 text-center">
          <div class="w-20 h-20 bg-white/5 rounded-full flex items-center justify-center mx-auto mb-6">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-10 h-10 text-white/20" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.172 9.172a4 4 0 015.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
            </svg>
          </div>
          <h3 class="text-2xl font-serif text-white mb-2">No dishes found</h3>
          <p class="text-white/40">Try searching for something else or browse another category.</p>
        </div>
      </section>
    </main>

    <!-- 7. Floating Order Button -->
    <div v-if="cart.length" class="fixed bottom-8 left-1/2 -translate-x-1/2 z-50 w-full max-w-[calc(100%-3rem)] md:max-w-md">
      <button 
        @click="isCartOpen = true"
        class="w-full bg-[#D9A05B] hover:bg-[#FFE4AD] text-black font-bold py-4 px-8 rounded-2xl shadow-[0_20px_50px_rgba(217,160,91,0.4)] transition-all duration-300 transform hover:-translate-y-1 flex items-center justify-between"
      >
        <div class="flex items-center gap-3">
          <div class="relative">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z" />
            </svg>
            <span class="absolute -top-2 -right-2 bg-black text-white text-[10px] w-5 h-5 rounded-full flex items-center justify-center border border-[#D9A05B]">
              {{ cartCount }}
            </span>
          </div>
          <span>View Order</span>
        </div>
        <span class="text-xl font-mono">{{ cartTotal }} ETB</span>
      </button>
    </div>

    <!-- 6. Item Detail Modal -->
    <Transition name="modal">
      <div v-if="isItemModalOpen" class="fixed inset-0 z-[60] flex items-center justify-center px-6">
        <div class="absolute inset-0 bg-black/90 backdrop-blur-md" @click="isItemModalOpen = false"></div>
        <div class="relative bg-[#111111] w-full max-w-2xl rounded-[2.5rem] overflow-hidden border border-white/10 shadow-3xl animate-in zoom-in-95 duration-300">
          <button @click="isItemModalOpen = false" class="absolute top-6 right-6 z-10 w-10 h-10 bg-black/50 hover:bg-black rounded-full flex items-center justify-center text-white/60 hover:text-white transition-all">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>

          <div class="flex flex-col md:flex-row h-full">
            <!-- Image Side -->
            <div class="w-full md:w-1/2 h-64 md:h-auto overflow-hidden">
              <img :src="selectedItem.image" :alt="selectedItem.name" class="w-full h-full object-cover" />
            </div>
            <!-- Info Side -->
            <div class="w-full md:w-1/2 p-10 flex flex-col">
              <div class="mb-6">
                <span class="text-[#D9A05B] text-xs font-bold uppercase tracking-widest mb-2 block">{{ selectedItem.category }}</span>
                <h2 class="text-3xl font-serif font-bold text-white mb-3">{{ selectedItem.name }}</h2>
                <div class="flex items-center text-sm text-[#D9A05B] mb-4">
                   <span class="mr-2">⭐ {{ selectedItem.rating }}</span>
                   <span class="w-1 h-1 bg-white/20 rounded-full mr-2"></span>
                   <span class="text-white/40">20-30 min</span>
                </div>
                <p class="text-white/60 leading-relaxed mb-6">{{ selectedItem.description }}</p>
                <div class="text-3xl font-bold font-mono text-white">{{ selectedItem.price }} ETB</div>
              </div>

              <!-- Quantity Selector -->
              <div class="mt-auto">
                <div class="flex items-center gap-6 mb-8">
                  <div class="flex items-center bg-white/5 border border-white/10 rounded-2xl p-1">
                    <button 
                      @click="selectedItem.quantity = Math.max(1, selectedItem.quantity - 1)"
                      class="w-10 h-10 hover:bg-white/5 rounded-xl flex items-center justify-center transition-all"
                    >
                      -
                    </button>
                    <span class="w-12 text-center font-bold text-lg">{{ selectedItem.quantity }}</span>
                    <button 
                      @click="selectedItem.quantity++"
                      class="w-10 h-10 hover:bg-white/5 rounded-xl flex items-center justify-center transition-all"
                    >
                      +
                    </button>
                  </div>
                </div>

                <button 
                  @click="addToCart(selectedItem)"
                  class="w-full bg-[#D9A05B] hover:bg-[#FFE4AD] text-black font-bold py-4 rounded-2xl transition-all duration-300 shadow-xl"
                >
                  Add to Order
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Transition>

    <!-- 8. Cart Drawer -->
    <Transition name="drawer">
      <div v-if="isCartOpen" class="fixed inset-0 z-[70] flex justify-end">
        <div class="absolute inset-0 bg-black/60 backdrop-blur-sm" @click="isCartOpen = false"></div>
        <div class="relative w-full max-w-md bg-[#0A0A0A] h-full shadow-2xl border-l border-white/5 flex flex-col">
          <!-- Drawer Header -->
          <div class="p-8 border-b border-white/5 flex items-center justify-between bg-[#111111]">
            <div>
              <h2 class="text-2xl font-serif font-bold">Your Order</h2>
              <p class="text-white/40 text-sm italic">Items ready for prep</p>
            </div>
            <button @click="isCartOpen = false" class="text-white/40 hover:text-white transition-colors">
              <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>
          </div>

          <!-- Drawer Body -->
          <div class="flex-1 overflow-y-auto p-8 space-y-6">
            <div v-if="cart.length === 0" class="h-full flex flex-col items-center justify-center text-center">
              <div class="w-20 h-20 bg-white/5 rounded-full flex items-center justify-center mb-6">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-10 h-10 text-white/20" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z" />
                </svg>
              </div>
              <p class="text-lg text-white/40">Your cart is empty</p>
            </div>

            <div v-for="item in cart" :key="'cart-' + item.id" class="flex items-center gap-4 group">
              <img :src="item.image" :alt="item.name" class="w-20 h-20 rounded-2xl object-cover border border-white/5" />
              <div class="flex-1">
                <h4 class="font-bold text-white mb-1">{{ item.name }}</h4>
                <div class="text-[#D9A05B] font-mono font-bold">{{ item.price }} ETB</div>
              </div>
              <!-- Mini Quantity Controller -->
              <div class="flex items-center bg-white/5 rounded-xl p-1 border border-white/5">
                <button @click="updateCartQuantity(item.id, -1)" class="w-7 h-7 hover:bg-white/10 rounded-lg flex items-center justify-center text-xs">-</button>
                <span class="w-7 text-center text-sm font-bold">{{ item.quantity }}</span>
                <button @click="updateCartQuantity(item.id, 1)" class="w-7 h-7 hover:bg-white/10 rounded-lg flex items-center justify-center text-xs">+</button>
              </div>
            </div>
          </div>

          <!-- Drawer Footer -->
          <div v-if="cart.length" class="p-8 bg-[#111111] border-t border-white/5 space-y-6">
            <div class="space-y-3">
              <div class="flex justify-between text-white/60">
                <span>Subtotal</span>
                <span>{{ cartTotal }} ETB</span>
              </div>
              <div class="flex justify-between text-white/60">
                <span>Service Fee</span>
                <span>0 ETB</span>
              </div>
              <div class="flex justify-between text-2xl font-bold text-white pt-3 border-t border-white/5">
                <span class="font-serif">Total</span>
                <span class="font-mono text-[#D9A05B]">{{ cartTotal }} ETB</span>
              </div>
            </div>
            <button class="w-full bg-[#D9A05B] hover:bg-[#FFE4AD] text-black font-bold py-5 rounded-[2rem] shadow-xl transition-all duration-300 transform active:scale-95 flex items-center justify-center gap-3">
              <span>Place Order</span>
              <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
              </svg>
            </button>
          </div>
        </div>
      </div>
    </Transition>

    <!-- 9. Footer Section -->
    <Footer />
  </div>
</template>

<style scoped>
.no-scrollbar::-webkit-scrollbar {
  display: none;
}
.no-scrollbar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}

/* Modal Transitions */
.modal-enter-active, .modal-leave-active {
  transition: opacity 0.3s ease;
}
.modal-enter-from, .modal-leave-to {
  opacity: 0;
}

/* Drawer Transitions */
.drawer-enter-active, .drawer-leave-active {
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}
.drawer-enter-from, .drawer-leave-to {
  transform: translateX(100%);
  opacity: 0;
}

.shadow-3xl {
  box-shadow: 0 40px 100px -20px rgba(0, 0, 0, 0.5);
}

/* Base fade-in for cards */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.main > * {
  animation: fadeIn 0.8s ease-out forwards;
}
</style>
