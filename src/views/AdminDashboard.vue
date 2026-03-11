<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()
const isSidebarOpen = ref(true)

const logout = () => {
  // Clear any auth data here
  localStorage.removeItem('authToken')
  router.push('/login')
}

const stats = [
  { name: 'Total Revenue', value: '$45,231.89', change: '+20.1%', icon: '💰' },
  { name: 'Active Orders', value: '356', change: '+12.5%', icon: '📜' },
  { name: 'New Customers', value: '+2,350', change: '+18.2%', icon: '👤' },
  { name: 'Table Occupancy', value: '78%', change: '+4.3%', icon: '🍽️' },
]
</script>

<template>
  <div class="min-h-screen bg-[#F8FAFC] flex font-sans">
    <!-- Sidebar -->
    <aside
      :class="[
        'bg-[#0A0A0A] text-white transition-all duration-300 ease-in-out z-20',
        isSidebarOpen ? 'w-64' : 'w-20',
      ]"
    >
      <div class="p-6 flex items-center justify-between">
        <div v-if="isSidebarOpen" class="text-[#A31621] text-2xl font-bold flex items-center">
          <span class="text-3xl -mt-1">P</span>
          <span class="tracking-tighter text-white">ringo</span>
          <span class="text-[#A31621]">Es</span>
        </div>
        <div v-else class="text-[#A31621] text-2xl font-bold w-full text-center">P</div>
        <button
          @click="isSidebarOpen = !isSidebarOpen"
          class="text-gray-400 hover:text-white lg:hidden"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
        </button>
      </div>

      <nav class="mt-6 px-4 space-y-2">
        <a href="#" class="flex items-center gap-3 px-4 py-3 rounded-xl bg-[#A31621] text-white">
          <span>🏠</span>
          <span v-if="isSidebarOpen">Dashboard</span>
        </a>
        <a
          href="#"
          class="flex items-center gap-3 px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 hover:text-white transition-colors"
        >
          <span>🍔</span>
          <span v-if="isSidebarOpen">Menu Items</span>
        </a>
        <a
          href="#"
          class="flex items-center gap-3 px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 hover:text-white transition-colors"
        >
          <span>📅</span>
          <span v-if="isSidebarOpen">Orders</span>
        </a>
        <a
          href="#"
          class="flex items-center gap-3 px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 hover:text-white transition-colors"
        >
          <span>👥</span>
          <span v-if="isSidebarOpen">Customers</span>
        </a>
        <a
          href="#"
          class="flex items-center gap-3 px-4 py-3 rounded-xl text-gray-400 hover:bg-white/5 hover:text-white transition-colors"
        >
          <span>⚙️</span>
          <span v-if="isSidebarOpen">Settings</span>
        </a>
      </nav>

      <div class="absolute bottom-8 left-0 w-full px-4">
        <button
          @click="logout"
          class="flex items-center gap-3 px-4 py-3 w-full rounded-xl text-red-400 hover:bg-red-400/10 transition-colors"
        >
          <span>🚪</span>
          <span v-if="isSidebarOpen">Logout</span>
        </button>
      </div>
    </aside>

    <!-- Main Content -->
    <main class="flex-1 flex flex-col overflow-hidden">
      <!-- Header -->
      <header class="bg-white border-b border-gray-100 px-8 py-4 flex items-center justify-between">
        <h2 class="text-xl font-bold text-gray-800">Dashboard Overview</h2>
        <div class="flex items-center gap-4">
          <div class="relative">
            <span class="absolute top-0 right-0 w-2 h-2 bg-red-500 rounded-full"></span>
            <span class="text-xl">🔔</span>
          </div>
          <div class="flex items-center gap-3 pl-4 border-l border-gray-100">
            <div class="text-right hidden sm:block">
              <p class="text-sm font-bold text-gray-800">Admin User</p>
              <p class="text-xs text-gray-400">admin@tizazgo.com</p>
            </div>
            <div
              class="w-10 h-10 rounded-full bg-[#A31621]/10 flex items-center justify-center text-[#A31621] font-bold"
            >
              A
            </div>
          </div>
        </div>
      </header>

      <!-- Dashboard Body -->
      <div class="flex-1 overflow-y-auto p-8">
        <div class="mb-8">
          <h1 class="text-3xl font-bold text-gray-900">Welcome back, Admin! 👋</h1>
          <p class="text-gray-500 mt-2">Here's what's happening with your restaurant today.</p>
        </div>

        <!-- Stats Grid -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
          <div
            v-for="stat in stats"
            :key="stat.name"
            class="bg-white p-6 rounded-2xl shadow-sm border border-gray-50 hover:shadow-md transition-shadow"
          >
            <div class="flex items-center justify-between mb-4">
              <div class="text-2xl">{{ stat.icon }}</div>
              <span
                :class="[
                  'text-xs font-bold px-2 py-1 rounded-full',
                  stat.change.startsWith('+')
                    ? 'bg-green-100 text-green-600'
                    : 'bg-red-100 text-red-600',
                ]"
              >
                {{ stat.change }}
              </span>
            </div>
            <p class="text-gray-500 text-sm font-medium">{{ stat.name }}</p>
            <h3 class="text-2xl font-bold text-gray-900 mt-1">{{ stat.value }}</h3>
          </div>
        </div>

        <!-- Placeholder for charts/tables -->
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
          <div
            class="lg:col-span-2 bg-white p-6 rounded-2xl shadow-sm border border-gray-50 h-[400px] flex items-center justify-center border-dashed"
          >
            <p class="text-gray-400 italic">Sales Analytics Chart Placeholder</p>
          </div>
          <div
            class="bg-white p-6 rounded-2xl shadow-sm border border-gray-50 h-[400px] flex items-center justify-center border-dashed"
          >
            <p class="text-gray-400 italic">Recent Notifications Placeholder</p>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap');

.font-sans {
  font-family: 'Plus Jakarta Sans', sans-serif;
}
</style>
