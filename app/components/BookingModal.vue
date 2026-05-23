<script setup>
import { ref } from 'vue'

const isBookingOpen = useState('isBookingOpen', () => false)

const form = ref({
  name: '',
  phone: '',
  date: '',
  people: 1,
  activity: 'Termales Rivera'
})

const success = ref(false)

const closeModal = () => {
  isBookingOpen.value = false
  success.value = false
}

const submitForm = () => {
  if (!form.value.name || !form.value.phone || !form.value.date) {
    alert('Por favor complete todos los campos obligatorios.')
    return
  }

  // Pre-fill WhatsApp URL
  const message = `Hola! Quiero planificar mi visita a Rivera:\n\n*Nombre:* ${form.value.name}\n*Teléfono:* ${form.value.phone}\n*Fecha:* ${form.value.date}\n*Personas:* ${form.value.people}\n*Interés:* ${form.value.activity}`
  const encodedText = encodeURIComponent(message)
  const whatsappUrl = `https://wa.me/573123456789?text=${encodedText}`
  
  // Show success and redirect
  success.value = true
  
  setTimeout(() => {
    window.open(whatsappUrl, '_blank')
    closeModal()
  }, 1200)
}
</script>

<template>
  <Transition name="fade">
    <div v-if="isBookingOpen" class="fixed inset-0 z-[100] flex items-center justify-center p-4">
      <!-- Backdrop -->
      <div class="absolute inset-0 bg-black/60 backdrop-blur-sm" @click="closeModal"></div>
      
      <!-- Modal Content -->
      <div class="relative bg-surface w-full max-w-lg rounded-2xl shadow-2xl border border-outline-variant/30 overflow-hidden transform transition-all duration-300 scale-100 flex flex-col max-h-[90vh]">
        <!-- Top bar/header -->
        <div class="bg-primary text-on-primary p-6">
          <div class="flex justify-between items-center">
            <h3 class="font-display text-2xl font-bold">Reserva tu Experiencia</h3>
            <button @click="closeModal" class="text-on-primary/80 hover:text-on-primary transition-colors">
              <span class="material-symbols-outlined text-2xl">close</span>
            </button>
          </div>
          <p class="text-on-primary-container text-xs mt-1">Planifica tu escapada y te contactamos con los operadores certificados.</p>
        </div>

        <!-- Form body -->
        <div class="p-6 overflow-y-auto flex-1">
          <div v-if="success" class="flex flex-col items-center justify-center py-8 text-center">
            <span class="material-symbols-outlined text-6xl text-surface-tint mb-4 animate-bounce">check_circle</span>
            <h4 class="font-display text-xl font-bold text-primary mb-2">¡Solicitud Procesada!</h4>
            <p class="text-on-surface-variant text-sm">Redireccionando a WhatsApp de reservas de Rivera...</p>
          </div>

          <form v-else @submit.prevent="submitForm" class="space-y-4">
            <div>
              <label class="block text-xs font-bold uppercase text-on-surface-variant mb-1">Nombre Completo *</label>
              <input 
                v-model="form.name"
                type="text" 
                required 
                placeholder="Ej. Juan Pérez"
                class="w-full px-4 py-2.5 rounded-lg border border-outline-variant bg-surface-container-lowest focus:outline-none focus:ring-2 focus:ring-primary/50 text-sm"
              />
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-bold uppercase text-on-surface-variant mb-1">WhatsApp *</label>
                <input 
                  v-model="form.phone"
                  type="tel" 
                  required 
                  placeholder="Ej. 312 345 6789"
                  class="w-full px-4 py-2.5 rounded-lg border border-outline-variant bg-surface-container-lowest focus:outline-none focus:ring-2 focus:ring-primary/50 text-sm"
                />
              </div>
              <div>
                <label class="block text-xs font-bold uppercase text-on-surface-variant mb-1">Fecha de Visita *</label>
                <input 
                  v-model="form.date"
                  type="date" 
                  required 
                  class="w-full px-4 py-2.5 rounded-lg border border-outline-variant bg-surface-container-lowest focus:outline-none focus:ring-2 focus:ring-primary/50 text-sm"
                />
              </div>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-xs font-bold uppercase text-on-surface-variant mb-1">Personas</label>
                <input 
                  v-model.number="form.people"
                  type="number" 
                  min="1" 
                  max="50"
                  class="w-full px-4 py-2.5 rounded-lg border border-outline-variant bg-surface-container-lowest focus:outline-none focus:ring-2 focus:ring-primary/50 text-sm"
                />
              </div>
              <div>
                <label class="block text-xs font-bold uppercase text-on-surface-variant mb-1">¿Qué quieres vivir?</label>
                <select 
                  v-model="form.activity"
                  class="w-full px-4 py-2.5 rounded-lg border border-outline-variant bg-surface-container-lowest focus:outline-none focus:ring-2 focus:ring-primary/50 text-sm"
                >
                  <option value="Termales Rivera">Termales de Rivera</option>
                  <option value="Ecoturismo y Cascadas">Cascadas y Ecoturismo</option>
                  <option value="Gastronomia Local">Gastronomía y Cholupa</option>
                  <option value="Ruta del Vino">Visita a Viñedos (La Ulloa)</option>
                  <option value="Hospedaje Campestre">Glamping / Cabaña Campestre</option>
                  <option value="Plan Fachada Tour">Tour Histórico Colonial</option>
                </select>
              </div>
            </div>

            <div class="pt-4">
              <button 
                type="submit" 
                class="w-full bg-secondary text-on-secondary py-3.5 rounded-lg font-bold text-sm hover:bg-secondary-container hover:shadow-lg transition-all transform hover:-translate-y-0.5"
              >
                Confirmar y Chatear
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </Transition>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
