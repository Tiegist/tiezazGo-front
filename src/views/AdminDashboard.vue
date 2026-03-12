<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()
const isSidebarOpen = ref(true)
const activeNav = ref('dashboard')

const logout = () => {
  localStorage.removeItem('authToken')
  router.push('/login')
}

const stats = [
  { name: 'Total Revenue', value: '$45,231.89', change: '+20.1%', positive: true, icon: 'revenue' },
  { name: 'Active Orders', value: '356', change: '+12.5%', positive: true, icon: 'orders' },
  { name: 'New Customers', value: '+2,350', change: '+18.2%', positive: true, icon: 'customers' },
  { name: 'Table Occupancy', value: '78%', change: '+4.3%', positive: true, icon: 'tables' },
]

const recentOrders = [
  { id: '#ORD-7291', customer: 'Sarah M.', items: 'Gourmet Burger x2', total: '$48.90', status: 'Preparing', time: '2 min ago' },
  { id: '#ORD-7290', customer: 'James K.', items: 'Seafood Platter', total: '$89.50', status: 'Delivered', time: '15 min ago' },
  { id: '#ORD-7289', customer: 'Emma W.', items: 'Heritage Beef', total: '$62.00', status: 'Ready', time: '22 min ago' },
  { id: '#ORD-7288', customer: 'Michael R.', items: 'Velvet Dessert x3', total: '$36.00', status: 'Delivered', time: '45 min ago' },
  { id: '#ORD-7287', customer: 'Lisa P.', items: 'Pizza Margherita', total: '$24.50', status: 'Preparing', time: '1 hr ago' },
]

const navItems = [
  { key: 'dashboard', label: 'Dashboard', icon: 'dashboard' },
  { key: 'menu', label: 'Menu Items', icon: 'menu' },
  { key: 'orders', label: 'Orders', icon: 'orders' },
  { key: 'customers', label: 'Customers', icon: 'customers' },
  { key: 'analytics', label: 'Analytics', icon: 'analytics' },
  { key: 'settings', label: 'Settings', icon: 'settings' },
]
</script>

<template>
  <div class="admin-dashboard min-h-screen bg-[#F5F3EF] flex">
    <!-- Dark Sidebar -->
    <aside
      :class="[
        'fixed left-0 top-0 h-screen bg-[#1a1710] transition-all duration-300 ease-in-out z-30 flex flex-col shadow-xl',
        isSidebarOpen ? 'w-64' : 'w-[72px]',
      ]"
    >
      <!-- Logo -->
      <div class="px-3 h-[52px] flex items-center justify-between border-b border-white/5 shrink-0">
        <div v-if="isSidebarOpen" class="flex items-center gap-2">
          <div class="w-7 h-7 bg-gradient-to-br from-[#E8B86D] to-[#B8860B] rounded-lg flex items-center justify-center shadow-md shadow-[#D9A05B]/20">
            <span class="text-black font-bold text-[10px]">V</span>
          </div>
          <span class="text-sm font-bold tracking-tight text-white">VenobHD</span>
        </div>
        <div v-else class="w-full flex justify-center">
          <div class="w-7 h-7 bg-gradient-to-br from-[#E8B86D] to-[#B8860B] rounded-lg flex items-center justify-center">
            <span class="text-black font-bold text-[10px]">V</span>
          </div>
        </div>
        <button @click="isSidebarOpen = !isSidebarOpen" class="text-white/25 hover:text-[#D9A05B] transition-colors hidden lg:block">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
            <path v-if="isSidebarOpen" stroke-linecap="round" stroke-linejoin="round" d="M11 19l-7-7 7-7m8 14l-7-7 7-7" />
            <path v-else stroke-linecap="round" stroke-linejoin="round" d="M13 5l7 7-7 7M5 5l7 7-7 7" />
          </svg>
        </button>
      </div>

      <!-- Navigation -->
      <nav class="flex-1 py-2.5 px-2 space-y-0.5 overflow-y-auto">
        <a
          v-for="item in navItems"
          :key="item.key"
          href="#"
          @click.prevent="activeNav = item.key"
          :class="[
            'flex items-center gap-2.5 px-2.5 py-2 rounded-lg text-[13px] font-medium transition-all duration-200',
            activeNav === item.key
              ? 'bg-gradient-to-r from-[#D9A05B]/20 to-transparent text-[#E8B86D]'
              : 'text-white/35 hover:text-white/60 hover:bg-white/[0.04]',
          ]"
        >
          <svg v-if="item.icon === 'dashboard'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 shrink-0" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="3" width="7" height="7" rx="1.5"/><rect x="14" y="3" width="7" height="7" rx="1.5"/><rect x="3" y="14" width="7" height="7" rx="1.5"/><rect x="14" y="14" width="7" height="7" rx="1.5"/></svg>
          <svg v-if="item.icon === 'menu'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 shrink-0" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M3 6h18M3 12h18M3 18h18"/></svg>
          <svg v-if="item.icon === 'orders'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 shrink-0" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2"/></svg>
          <svg v-if="item.icon === 'customers'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 shrink-0" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87M16 3.13a4 4 0 010 7.75"/></svg>
          <svg v-if="item.icon === 'analytics'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 shrink-0" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M18 20V10M12 20V4M6 20v-6"/></svg>
          <svg v-if="item.icon === 'settings'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 shrink-0" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 00.33 1.82l.06.06a2 2 0 010 2.83 2 2 0 01-2.83 0l-.06-.06a1.65 1.65 0 00-1.82-.33 1.65 1.65 0 00-1 1.51V21a2 2 0 01-2 2 2 2 0 01-2-2v-.09A1.65 1.65 0 009 19.4a1.65 1.65 0 00-1.82.33l-.06.06a2 2 0 01-2.83 0 2 2 0 010-2.83l.06-.06A1.65 1.65 0 004.68 15a1.65 1.65 0 00-1.51-1H3a2 2 0 01-2-2 2 2 0 012-2h.09A1.65 1.65 0 004.6 9a1.65 1.65 0 00-.33-1.82l-.06-.06a2 2 0 010-2.83 2 2 0 012.83 0l.06.06A1.65 1.65 0 009 4.68a1.65 1.65 0 001-1.51V3a2 2 0 012-2 2 2 0 012 2v.09a1.65 1.65 0 001 1.51 1.65 1.65 0 001.82-.33l.06-.06a2 2 0 012.83 0 2 2 0 010 2.83l-.06.06a1.65 1.65 0 00-.33 1.82V9a1.65 1.65 0 001.51 1H21a2 2 0 012 2 2 2 0 01-2 2h-.09a1.65 1.65 0 00-1.51 1z"/></svg>
          <span v-if="isSidebarOpen">{{ item.label }}</span>
        </a>
      </nav>

      <!-- Logout -->
      <div class="px-2 py-2.5 border-t border-white/5 shrink-0">
        <button @click="logout" class="flex items-center gap-2.5 px-2.5 py-2 w-full rounded-lg text-[13px] font-medium text-red-400/60 hover:text-red-400 hover:bg-red-400/5 transition-all">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 shrink-0" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M9 21H5a2 2 0 01-2-2V5a2 2 0 012-2h4"/><polyline points="16 17 21 12 16 7"/><line x1="21" y1="12" x2="9" y2="12"/></svg>
          <span v-if="isSidebarOpen">Logout</span>
        </button>
      </div>
    </aside>

    <!-- Main Content -->
    <main :class="['flex-1 flex flex-col min-h-screen transition-all duration-300', isSidebarOpen ? 'ml-64' : 'ml-[72px]']">
      <!-- Top Header -->
      <header class="h-16 bg-white border-b border-gray-100 px-6 flex items-center justify-between sticky top-0 z-20 shrink-0">
        <div class="flex items-center gap-3">
          <button @click="isSidebarOpen = !isSidebarOpen" class="lg:hidden text-gray-400 hover:text-[#B8860B] transition-colors">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" /></svg>
          </button>
          <h2 class="text-sm font-semibold text-gray-700">Dashboard Overview</h2>
        </div>

        <div class="flex items-center gap-3">
          <!-- Search -->
          <div class="hidden md:flex items-center bg-gray-50 border border-gray-100 rounded-lg px-3 py-1.5 gap-2 w-44">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-3.5 h-3.5 text-gray-300" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
            <input type="text" placeholder="Search..." class="bg-transparent border-none outline-none text-xs text-gray-600 placeholder-gray-300 w-full" />
          </div>

          <!-- Notification -->
          <button class="relative p-1.5 rounded-lg hover:bg-gray-50 transition-colors">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 text-gray-400" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M18 8A6 6 0 006 8c0 7-3 9-3 9h18s-3-2-3-9M13.73 21a2 2 0 01-3.46 0"/></svg>
            <span class="absolute top-1 right-1 w-1.5 h-1.5 bg-[#D9A05B] rounded-full"></span>
          </button>

          <!-- Profile -->
          <div class="flex items-center gap-2.5 pl-3 border-l border-gray-100">
            <div class="text-right hidden sm:block">
              <p class="text-xs font-semibold text-gray-700">Admin User</p>
              <p class="text-[11px] text-gray-400">admin@tizazgo.com</p>
            </div>
            <div class="w-8 h-8 rounded-lg bg-gradient-to-br from-[#E8B86D] to-[#B8860B] flex items-center justify-center text-white text-[11px] font-bold shadow-sm">
              A
            </div>
          </div>
        </div>
      </header>

      <!-- Dashboard Body -->
      <div class="flex-1 overflow-y-auto p-5 lg:p-6">
        <!-- Welcome -->
        <div class="mb-5">
          <h1 class="text-xl font-bold text-gray-800">Welcome back, Admin 👋</h1>
          <p class="text-gray-400 text-sm mt-0.5">Here's what's happening with your restaurant today.</p>
        </div>

        <!-- Stats Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-4 gap-3 mb-5">
          <div
            v-for="stat in stats"
            :key="stat.name"
            class="group bg-white rounded-xl p-4 border border-gray-100 hover:border-[#D9A05B]/30 hover:shadow-md hover:shadow-[#D9A05B]/5 transition-all duration-300"
          >
            <div class="flex items-center justify-between mb-3">
              <div class="w-8 h-8 rounded-lg bg-[#D9A05B]/8 flex items-center justify-center group-hover:bg-[#D9A05B]/12 transition-colors">
                <svg v-if="stat.icon === 'revenue'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 text-[#B8860B]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><line x1="12" y1="1" x2="12" y2="23"/><path d="M17 5H9.5a3.5 3.5 0 000 7h5a3.5 3.5 0 010 7H6"/></svg>
                <svg v-if="stat.icon === 'orders'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 text-[#B8860B]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2"/></svg>
                <svg v-if="stat.icon === 'customers'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 text-[#B8860B]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M20 21v-2a4 4 0 00-4-4H8a4 4 0 00-4 4v2"/><circle cx="12" cy="7" r="4"/></svg>
                <svg v-if="stat.icon === 'tables'" xmlns="http://www.w3.org/2000/svg" class="w-4 h-4 text-[#B8860B]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/></svg>
              </div>
              <span
                :class="[
                  'text-xs font-semibold px-1.5 py-0.5 rounded-md',
                  stat.positive ? 'bg-emerald-50 text-emerald-600' : 'bg-red-50 text-red-500',
                ]"
              >
                {{ stat.change }}
              </span>
            </div>
            <p class="text-gray-400 text-sm font-medium">{{ stat.name }}</p>
            <h3 class="text-xl font-bold text-gray-800 mt-0.5">{{ stat.value }}</h3>
          </div>
        </div>

        <!-- Chart + Recent Orders -->
        <div class="grid grid-cols-1 xl:grid-cols-3 gap-3">
          <!-- Sales Chart -->
          <div class="xl:col-span-2 bg-white rounded-xl border border-gray-100 overflow-hidden">
            <div class="px-4 py-3 border-b border-gray-50 flex items-center justify-between">
              <div>
                <h3 class="text-sm font-semibold text-gray-700">Sales Analytics</h3>
                <p class="text-xs text-gray-400 mt-0.5">Revenue overview for the current period</p>
              </div>
              <div class="flex gap-1">
                <button class="px-2.5 py-1 rounded-md text-xs font-medium bg-[#D9A05B]/10 text-[#B8860B] border border-[#D9A05B]/15">Week</button>
                <button class="px-2.5 py-1 rounded-md text-xs font-medium text-gray-400 hover:text-gray-600 hover:bg-gray-50 transition-colors">Month</button>
                <button class="px-2.5 py-1 rounded-md text-xs font-medium text-gray-400 hover:text-gray-600 hover:bg-gray-50 transition-colors">Year</button>
              </div>
            </div>
            <div class="h-[260px] flex items-end justify-around px-4 py-4 gap-2">
              <div v-for="(height, i) in [45, 65, 35, 80, 55, 90, 70]" :key="i" class="flex flex-col items-center gap-2 flex-1">
                <div
                  class="w-full rounded-t-md bg-gradient-to-t from-[#D9A05B]/25 to-[#E8B86D]/8 hover:from-[#D9A05B]/40 hover:to-[#E8B86D]/15 transition-all duration-300 cursor-pointer"
                  :style="{ height: height + '%' }"
                ></div>
                <span class="text-[11px] text-gray-300 font-medium">{{ ['Mon','Tue','Wed','Thu','Fri','Sat','Sun'][i] }}</span>
              </div>
            </div>
          </div>

          <!-- Recent Orders -->
          <div class="bg-white rounded-xl border border-gray-100 overflow-hidden">
            <div class="px-4 py-3 border-b border-gray-50 flex items-center justify-between">
              <h3 class="text-sm font-semibold text-gray-700">Recent Orders</h3>
              <a href="#" class="text-xs text-[#B8860B] hover:text-[#D9A05B] transition-colors font-medium">View All</a>
            </div>
            <div class="divide-y divide-gray-50">
              <div
                v-for="order in recentOrders"
                :key="order.id"
                class="px-4 py-2.5 hover:bg-gray-50/50 transition-colors"
              >
                <div class="flex items-center justify-between mb-1">
                  <div class="flex items-center gap-2">
                    <span class="text-xs font-mono text-gray-300">{{ order.id }}</span>
                    <span class="text-sm font-semibold text-gray-700">{{ order.customer }}</span>
                  </div>
                  <span class="text-sm font-bold text-gray-800">{{ order.total }}</span>
                </div>
                <div class="flex items-center justify-between">
                  <span class="text-xs text-gray-400">{{ order.items }}</span>
                  <div class="flex items-center gap-2">
                    <span
                      :class="[
                        'text-[11px] font-semibold px-1.5 py-0.5 rounded-md',
                        order.status === 'Delivered' ? 'bg-emerald-50 text-emerald-600' :
                        order.status === 'Ready' ? 'bg-blue-50 text-blue-600' :
                        'bg-amber-50 text-amber-600'
                      ]"
                    >{{ order.status }}</span>
                    <span class="text-[11px] text-gray-300">{{ order.time }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Bottom Row -->
        <div class="grid grid-cols-1 md:grid-cols-2 gap-3 mt-3">
          <!-- Popular Items -->
          <div class="bg-white rounded-xl border border-gray-100 overflow-hidden">
            <div class="px-4 py-3 border-b border-gray-50">
              <h3 class="text-sm font-semibold text-gray-700">Popular Items</h3>
              <p class="text-xs text-gray-400 mt-0.5">Top selling items today</p>
            </div>
            <div class="p-4 space-y-3">
              <div v-for="(item, i) in [
                { name: 'Gourmet Burger', sold: 142, pct: 85 },
                { name: 'Seafood Platter', sold: 98, pct: 65 },
                { name: 'Heritage Beef', sold: 76, pct: 50 },
                { name: 'Velvet Dessert', sold: 54, pct: 35 },
              ]" :key="i" class="flex items-center gap-3">
                <span class="text-xs text-gray-300 w-4 text-right font-mono">#{{ i + 1 }}</span>
                <div class="flex-1">
                  <div class="flex items-center justify-between mb-1">
                    <span class="text-sm font-medium text-gray-600">{{ item.name }}</span>
                    <span class="text-xs text-gray-400">{{ item.sold }} sold</span>
                  </div>
                  <div class="h-1.5 bg-gray-100 rounded-full overflow-hidden">
                    <div class="h-full bg-gradient-to-r from-[#D9A05B] to-[#E8B86D] rounded-full transition-all duration-500" :style="{ width: item.pct + '%' }"></div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Quick Actions -->
          <div class="bg-white rounded-xl border border-gray-100 overflow-hidden">
            <div class="px-4 py-3 border-b border-gray-50">
              <h3 class="text-sm font-semibold text-gray-700">Quick Actions</h3>
              <p class="text-xs text-gray-400 mt-0.5">Frequently used tasks</p>
            </div>
            <div class="p-4 grid grid-cols-2 gap-2">
              <button class="flex flex-col items-center gap-2 p-3 rounded-lg bg-gray-50/50 border border-gray-100 hover:border-[#D9A05B]/30 hover:bg-[#D9A05B]/5 transition-all group">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-gray-300 group-hover:text-[#B8860B] transition-colors" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="16"/><line x1="8" y1="12" x2="16" y2="12"/></svg>
                <span class="text-xs font-medium text-gray-400 group-hover:text-gray-600">New Order</span>
              </button>
              <button class="flex flex-col items-center gap-2 p-3 rounded-lg bg-gray-50/50 border border-gray-100 hover:border-[#D9A05B]/30 hover:bg-[#D9A05B]/5 transition-all group">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-gray-300 group-hover:text-[#B8860B] transition-colors" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M11 4H4a2 2 0 00-2 2v14a2 2 0 002 2h14a2 2 0 002-2v-7"/><path d="M18.5 2.5a2.121 2.121 0 013 3L12 15l-4 1 1-4 9.5-9.5z"/></svg>
                <span class="text-xs font-medium text-gray-400 group-hover:text-gray-600">Edit Menu</span>
              </button>
              <button class="flex flex-col items-center gap-2 p-3 rounded-lg bg-gray-50/50 border border-gray-100 hover:border-[#D9A05B]/30 hover:bg-[#D9A05B]/5 transition-all group">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-gray-300 group-hover:text-[#B8860B] transition-colors" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><line x1="19" y1="8" x2="19" y2="14"/><line x1="22" y1="11" x2="16" y2="11"/></svg>
                <span class="text-xs font-medium text-gray-400 group-hover:text-gray-600">Add Customer</span>
              </button>
              <button class="flex flex-col items-center gap-2 p-3 rounded-lg bg-gray-50/50 border border-gray-100 hover:border-[#D9A05B]/30 hover:bg-[#D9A05B]/5 transition-all group">
                <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-gray-300 group-hover:text-[#B8860B] transition-colors" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/></svg>
                <span class="text-xs font-medium text-gray-400 group-hover:text-gray-600">Reports</span>
              </button>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');

.admin-dashboard {
  font-family: 'Inter', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
