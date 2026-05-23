<script setup>
import { ref, computed } from 'vue'

useSeoMeta({
  title: 'Agenda de Tradición - Eventos en Rivera Huila',
  description: 'Descubre los festivales, ferias y celebraciones culturales de Rivera, Huila. Desde el Festival del Retorno hasta la Feria de la Achira.'
})

const selectedSeason = ref('todos')

const seasons = [
  { id: 'todos', label: 'Todo el Año' },
  { id: 'mitad', label: 'Mitad de Año' },
  { id: 'fin', label: 'Fin de Año' }
]

const events = [
  {
    id: 1,
    title: 'Festival del Retorno',
    month: 'JUNIO',
    season: 'mitad',
    desc: 'El corazón de nuestra cultura late al ritmo del Sanjuanero Huilense. Rivera recibe a sus hijos y visitantes con muestras folclóricas, música de cuerdas y la elegancia de nuestras danzas tradicionales.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAAE2bIxozoLSpKbZdini3nPv2kNuFmeWw6o_mNrGgArkmP3IoGTmgEpYk8OsII9l9hpS2ZZc4zyx9rqVZg71afUZF7cPLvpSgPF_AIqlNqycWtBz7RZqgDwqFKbKcP4feFRnHxzTpA140lZZE1yEjxmzHh7zMb7aVbUE1grB-Z3-ejngDBCgOsmrb5ntp6udiGTRsUUgp9o1bNNMCaFovT-3LKATb8u7dW0RJZETn2huSQ4zFijGRrqZK6NlXJy4dUzdFHYhL8YAs',
    featured: true
  },
  {
    id: 2,
    title: 'Fiestas de San Roque',
    month: 'AGOSTO',
    season: 'mitad',
    desc: 'Celebraciones religiosas y culturales en honor a nuestro patrono San Roque, uniendo la fe con desfiles y la alegría del pueblo.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCEAdEek_wr3koQRzNL-p59U7mFocux2liBIrZkn-bctAt35p6PE8clulEQ8pineZl07Ca6nD7-zR9CLHWEsIbTuGE0rGrQrKe1Ahj2OzYVzlKZCQNnMxWzBZFGEvEOHLlSvwnyJpnSiJPCTU7nVRZL2tnAFGvhJzxj_ysLVNYfEH5eWiHsKLQ1rz4r2W3jgcPMG3WoLGOIB0TC4zfoNvFVxc3Cses3LuvmKZDZQl1Rt96YpyL6837ValErddg02yBVp-Z3qkZzKEw',
    featured: false
  },
  {
    id: 3,
    title: 'Luces de Navidad',
    month: 'DICIEMBRE',
    season: 'fin',
    desc: 'Rivera se transforma en un pesebre de luz. Las calles coloniales brillan bajo miles de bombillas, creando una atmósfera mágica para caminar en familia.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCrorAXMzQjpUdwA98QkSIeIikmRwp7LX2B-x_bp_jNscxaXk66KiHf-hDBMklkM6vwyFK0aw5LKRkpfWUffoHcNxplznIAkKWRssvxzqO1bTYHDNJWLixEusyvRneOpQIYZ6POWJvHnjg8Y2MGIOSZTyDExwwdmey0eIvkLfUXPPvz3kR9A_4leWMEDUf5NvPjPyTV4uk1ObJ5m6J-ie2pTt_LIXddz2vMA3vcbhoT0r-jb52MF1peBVQkLYFhCpgEZ2StUCC9heo',
    featured: true
  }
]

const filteredEvents = computed(() => {
  if (selectedSeason.value === 'todos') return events
  return events.filter(e => e.season === selectedSeason.value)
})
</script>

<template>
  <div>
    <!-- Hero Section -->
    <section class="relative h-[55vh] flex items-center justify-center overflow-hidden bg-primary">
      <div class="absolute inset-0 opacity-40">
        <img 
          class="w-full h-full object-cover" 
          src="https://lh3.googleusercontent.com/aida-public/AB6AXuClydU6Y76HDEdsB8PO2YyK0qIaLC7ghqWzDx9h_FnZwYZQhQwM9ABC2p-QYTrRYIYnxZqT-IbbA3Twp9Hb9_brLKnWj3MEr3f3Aaa1Fs3_c2W8rVD8zTP2ym2049ZuBW_pEHEJF4qtvRoEw4v8ZMnA1lF-DCnlBLH8L2qveJe1nfAK06Jr4DHHf5ulm81Jd3QaLTIzqsZHBnW-v1KQfcABvE1RUIJBHlE5PXZ_WMQagIE4gW4mpdByARCbVXKq0gewfOC5XBF9g6g"
          alt="Atardecer en Rivera"
        />
      </div>
      <div class="relative z-10 text-center px-margin-mobile">
        <h1 class="font-display text-4xl md:text-5xl text-on-primary mb-4 font-bold drop-shadow-md">Agenda de Tradición</h1>
        <p class="font-body text-base md:text-lg text-on-primary/90 max-w-2xl mx-auto italic">
          Un recorrido por el alma de Rivera a través de sus fiestas, sabores, leyendas y gente.
        </p>
      </div>
    </section>

    <!-- Events Bento Grid -->
    <section class="py-20 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-end mb-12 gap-6">
        <div class="max-w-xl">
          <span class="text-xs font-bold text-secondary uppercase tracking-[0.2em] mb-2 block">Calendario Anual</span>
          <h2 class="font-display text-3xl md:text-4xl text-primary font-bold">Nuestros Eventos Principales</h2>
          <p class="text-on-surface-variant text-sm mt-4 leading-relaxed">
            Rivera se viste de gala durante todo el año. Desde las notas del Sanjuanero Huilense en San Pedro hasta el aroma y sabor del bizcocho de achira.
          </p>
        </div>
        
        <!-- Season Filters -->
        <div class="flex bg-surface-container rounded-full p-1 border border-outline-variant/30">
          <button 
            v-for="season in seasons" 
            :key="season.id"
            @click="selectedSeason = season.id"
            class="px-5 py-2 rounded-full font-bold text-xs transition-all whitespace-nowrap"
            :class="selectedSeason === season.id 
              ? 'bg-primary text-on-primary shadow-sm' 
              : 'text-on-surface-variant hover:text-primary'"
          >
            {{ season.label }}
          </button>
        </div>
      </div>

      <!-- Grid layout -->
      <div class="grid grid-cols-1 md:grid-cols-12 gap-gutter">
        
        <!-- Dynamic rendering of selected events -->
        <template v-for="event in filteredEvents" :key="event.id">
          <!-- Featured Event (Large layout: cols 8) -->
          <div 
            v-if="event.featured"
            class="md:col-span-8 group relative overflow-hidden rounded-xl bg-white shadow-md hover:shadow-xl transition-all duration-500 flex flex-col justify-between"
          >
            <div class="h-80 relative overflow-hidden">
              <img :alt="event.title" class="w-full h-full object-cover group-hover:scale-103 transition-transform duration-700" :src="event.img" />
              <div class="absolute top-6 left-6 bg-primary text-on-primary px-4 py-1 rounded-full text-xs font-bold tracking-wider">{{ event.month }}</div>
            </div>
            <div class="p-8">
              <h3 class="font-display text-2xl text-primary mb-3 font-bold">{{ event.title }}</h3>
              <p class="text-on-surface-variant text-sm mb-6 leading-relaxed">{{ event.desc }}</p>
              <NuxtLink to="/planifica" class="inline-flex items-center gap-2 text-secondary font-bold text-xs hover:underline">
                Conocer cronograma <span class="material-symbols-outlined text-sm">arrow_forward</span>
              </NuxtLink>
            </div>
          </div>

          <!-- Normal Event (Standard layout: cols 4) -->
          <div 
            v-else
            class="md:col-span-4 group relative overflow-hidden rounded-xl bg-white shadow-md hover:shadow-xl transition-all duration-500 flex flex-col justify-between"
          >
            <div class="h-64 relative overflow-hidden">
              <img :alt="event.title" class="w-full h-full object-cover group-hover:scale-103 transition-transform duration-700" :src="event.img" />
              <div class="absolute top-4 left-4 bg-tertiary text-on-tertiary px-4 py-1 rounded-full text-xs font-bold tracking-wider">{{ event.month }}</div>
            </div>
            <div class="p-6">
              <h3 class="font-display text-xl text-primary mb-2 font-bold">{{ event.title }}</h3>
              <p class="text-on-surface-variant text-sm leading-relaxed mb-6">{{ event.desc }}</p>
              <NuxtLink to="/planifica" class="inline-flex items-center gap-2 text-secondary font-bold text-xs hover:underline">
                Saber más <span class="material-symbols-outlined text-sm">arrow_forward</span>
              </NuxtLink>
            </div>
          </div>
        </template>

        <!-- Static Gastronomy Side Column (if "mitad" not explicitly filtered to empty) -->
        <div 
          v-if="selectedSeason === 'todos' || selectedSeason === 'mitad'"
          class="md:col-span-4 flex flex-col gap-gutter justify-between"
        >
          <div class="flex-1 group relative overflow-hidden rounded-xl bg-secondary-container/10 p-8 border border-secondary-container/20 flex flex-col justify-between min-h-[180px]">
            <div class="flex justify-between items-start mb-4">
              <span class="bg-secondary text-on-secondary px-3 py-1 rounded-full text-[10px] font-bold tracking-wider">TODO EL AÑO</span>
              <span class="material-symbols-outlined text-secondary text-3xl">restaurant</span>
            </div>
            <div>
              <h3 class="font-display text-lg text-primary mb-2 font-bold">Feria de la Achira</h3>
              <p class="text-on-surface-variant text-sm leading-relaxed">
                Un homenaje gastronómico al bizcocho de achira tradicional y los postres artesanales de leche de Rivera.
              </p>
            </div>
          </div>

          <div class="flex-1 group relative overflow-hidden rounded-xl shadow-md min-h-[180px] h-48">
            <img 
              class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-700" 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuCP2S9EUZc64pbi6M4wDNJoNCvZHzklwaqPGU00RkUCD8UZ1kY4Cyn-ZKryGX6i0HdNZfJki1IHHCxbCG81PS3y3rGr1vxYu5R828dsYwjaO8ko9Aw0DVNBfs6Xf1nfdx73Gd2-vJo7wXg7gx7xSbJaZGOaA_7nnYBDOdbCVrZSrrtC3fk0wMddGiXyO1P3eV87BKOV2dubnNP13NBlXd2qUMdnXqv_rNyoT2OCdng73rAlbqpcZgDM-yjoJH6wBvGyQSTThkeo25A"
              alt="Bizcochos de achira"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent flex items-end p-6">
              <p class="text-white font-display text-lg font-bold">Sabores de Rivera</p>
            </div>
          </div>
        </div>

      </div>
    </section>

    <!-- Newsletter Section -->
    <section class="py-24 bg-surface-container-high relative overflow-hidden">
      <div class="absolute -right-20 -top-20 w-64 h-64 bg-primary/5 rounded-full blur-3xl"></div>
      <div class="absolute -left-20 -bottom-20 w-64 h-64 bg-secondary/5 rounded-full blur-3xl"></div>
      <div class="px-margin-mobile md:px-margin-desktop max-w-2xl mx-auto text-center relative z-10">
        <span class="material-symbols-outlined text-secondary text-5xl mb-6" style="font-variation-settings: 'FILL' 1;">mail</span>
        <h2 class="font-display text-2xl md:text-3xl text-primary mb-4 font-bold">Suscríbete al Boletín de Eventos</h2>
        <p class="text-on-surface-variant text-sm mb-10 leading-relaxed max-w-lg mx-auto">
          No te pierdas ni un solo momento de nuestra tradición. Recibe recordatorios mensuales y guías exclusivas de viaje directamente en tu correo.
        </p>
        <form class="flex flex-col sm:flex-row gap-4 max-w-md mx-auto" @submit.prevent="alert('¡Gracias por suscribirse!')">
          <input 
            required
            class="flex-grow px-6 py-4 rounded-lg bg-surface border border-outline-variant focus:border-primary focus:ring-2 focus:ring-primary/40 outline-none text-sm text-on-surface" 
            placeholder="Tu correo electrónico" 
            type="email"
          />
          <button 
            class="bg-primary text-on-primary px-8 py-4 rounded-lg font-bold text-xs uppercase tracking-wider hover:shadow-lg transition-all" 
            type="submit"
          >
            Suscribirme
          </button>
        </form>
        <p class="text-[10px] text-on-surface-variant/60 mt-6 font-semibold">Respetamos tu privacidad. Puedes darte de baja cuando quieras.</p>
      </div>
    </section>
  </div>
</template>
