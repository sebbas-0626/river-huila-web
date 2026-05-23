<script setup>
const isBookingOpen = useState('isBookingOpen', () => false)

const openBooking = () => {
  isBookingOpen.value = true
}
</script>

<template>
  <div class="bg-background text-on-surface font-sans selection:bg-primary-fixed selection:text-on-primary-fixed min-h-screen flex flex-col">
    <!-- Main Header -->
    <AppHeader />

    <!-- Page Content -->
    <main class="pt-20 flex-grow">
      <slot />
    </main>

    <!-- Main Footer -->
    <AppFooter />

    <!-- Booking Modal -->
    <BookingModal />

    <!-- Global Floating Action Button (FAB) -->
    <button 
      @click="openBooking"
      class="fixed bottom-8 right-8 bg-secondary text-on-secondary p-4 rounded-full shadow-2xl z-40 hover:scale-110 active:scale-95 transition-transform group flex items-center justify-center"
      aria-label="Planea tu viaje"
    >
      <span class="material-symbols-outlined font-fill" style="font-variation-settings: 'FILL' 1;">calendar_month</span>
      <span class="absolute right-full mr-4 bg-surface px-4 py-2 rounded-lg text-secondary font-bold text-xs shadow-lg opacity-0 group-hover:opacity-100 transition-opacity whitespace-nowrap pointer-events-none border border-outline-variant/30">
        Planea tu Viaje
      </span>
    </button>
  </div>
</template>

<style>
/* Custom style for the filled icon font-variation */
.font-fill {
  font-variation-settings: 'FILL' 1, 'wght' 400, 'GRAD' 0, 'opsz' 24;
}
</style>
