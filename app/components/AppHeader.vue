<script setup>
import { ref } from 'vue'

const isBookingOpen = useState('isBookingOpen', () => false)
const mobileMenuOpen = ref(false)

const navLinks = [
  { name: 'Inicio', path: '/' },
  { name: 'Tradición', path: '/tradicion' },
  { name: 'Lugares', path: '/lugares' },
  { name: 'Blog', path: '/blog' },
  { name: 'Directorio', path: '/directorio' },
  { name: 'Planifica', path: '/planifica' },
  { name: 'Agenda', path: '/agenda' }
]

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}

const openBooking = () => {
  isBookingOpen.value = true
  closeMobileMenu()
}
</script>

<template>
  <nav class="fixed top-0 w-full bg-surface/90 backdrop-blur-md shadow-sm z-50 transition-all duration-300">
    <div class="flex justify-between items-center px-margin-mobile md:px-margin-desktop h-20 max-w-container-max mx-auto">
      <NuxtLink to="/" class="font-display text-2xl text-primary font-bold tracking-tight hover:opacity-90 transition-opacity">
        Rivera Turística
      </NuxtLink>

      <!-- Desktop Nav -->
      <div class="hidden xl:flex items-center gap-6">
        <NuxtLink 
          v-for="link in navLinks" 
          :key="link.path"
          :to="link.path"
          class="text-on-surface-variant hover:text-primary transition-colors font-body font-medium text-sm py-1"
          active-class="text-secondary border-b-2 border-secondary font-bold"
        >
          {{ link.name }}
        </NuxtLink>
      </div>

      <!-- Action Button & Mobile Toggle -->
      <div class="flex items-center gap-4">
        <button 
          @click="openBooking"
          class="bg-primary text-on-primary px-5 py-2 rounded-full font-semibold text-sm hover:bg-primary-container transition-all duration-300 transform hover:scale-105 active:scale-95 shadow-sm"
        >
          Reservar
        </button>
        <button 
          @click="toggleMobileMenu"
          class="xl:hidden text-on-surface-variant focus:outline-none p-1"
          aria-label="Toggle Menu"
        >
          <span class="material-symbols-outlined text-2xl">
            {{ mobileMenuOpen ? 'close' : 'menu' }}
          </span>
        </button>
      </div>
    </div>

    <!-- Mobile Drawer Overlay -->
    <div 
      v-if="mobileMenuOpen" 
      class="fixed inset-0 top-20 bg-black/40 backdrop-blur-sm z-40 xl:hidden transition-all duration-300"
      @click="closeMobileMenu"
    />

    <!-- Mobile Drawer Content -->
    <div 
      class="fixed top-20 right-0 w-64 h-[calc(100vh-5rem)] bg-surface shadow-xl z-50 xl:hidden transform transition-transform duration-300 ease-in-out"
      :class="mobileMenuOpen ? 'translate-x-0' : 'translate-x-full'"
    >
      <div class="flex flex-col p-6 gap-4">
        <NuxtLink 
          v-for="link in navLinks" 
          :key="link.path"
          :to="link.path"
          class="text-on-surface-variant hover:text-primary transition-colors font-body text-base py-2 border-b border-surface-variant/30"
          active-class="text-secondary font-bold pl-2 border-l-2 border-l-secondary border-b-transparent"
          @click="closeMobileMenu"
        >
          {{ link.name }}
        </NuxtLink>
        <button 
          @click="openBooking"
          class="mt-4 w-full bg-secondary text-on-secondary py-3 rounded-lg font-semibold text-center hover:bg-secondary-container transition-all"
        >
          Reservar Ahora
        </button>
      </div>
    </div>
  </nav>
</template>
