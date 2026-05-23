<script setup>
import { ref, computed } from 'vue'

useSeoMeta({
  title: 'Directorio Local - Hospedajes y Gastronomía en Rivera',
  description: 'Encuentra dónde hospedarte y dónde comer en Rivera, Huila. Hoteles coloniales, glampings campestres, restaurantes y dulcerías tradicionales.'
})

const searchQuery = ref('')
const selectedCategory = ref('todos')

const categories = [
  { id: 'todos', label: 'Todos', icon: 'all_inclusive' },
  { id: 'glampings', label: 'Glampings', icon: 'bed' },
  { id: 'restaurantes', label: 'Restaurantes', icon: 'restaurant' },
  { id: 'dulcerias', label: 'Dulcerías', icon: 'bakery_dining' },
  { id: 'fincas', label: 'Fincas', icon: 'nature_people' }
]

const accommodations = [
  {
    id: 1,
    name: 'Los Domos del Sol',
    category: 'glampings',
    rating: '4.9',
    tag: 'GLAMPING',
    desc: 'Inmersión total en la naturaleza con el confort de un hotel de lujo y vistas espectaculares.',
    location: 'Vereda El Salado, Rivera',
    phone: '+57 310 123 4567',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDXtCVj5utUcSPXckwq4wh1beVxFrz_qYrmU2vaZuLbcC6BKxbhEuejWyumbusbgtlyOQqZju3GJXhbkW6YJucigkzBOmouIz2PUOWXpIVY_CYkQ2uHerpSS_Jn6h0baz7P4fzDPiSa3sNSoRwcHec9lnKT48FmFLMdNR15ESwWyME5HBGHOzH4XJkqkInhQg3gC40LnrMHQnQNODVJJbkwunC_Fa1wv486pqtAP5lg9H3R_LPcO3CAYPWQVYSWLQBEW3Z5qJs72kw'
  },
  {
    id: 2,
    name: 'Casona La Rivera',
    category: 'fincas',
    rating: '4.8',
    tag: 'COLONIAL',
    desc: 'Arquitectura histórica conservada con hermosos jardines internos y confort colonial.',
    location: 'Carrera 4 # 5-20, Centro',
    phone: '+57 312 987 6543',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAsmnlrn5kjR9Xv-HQfsMvzwcrw8q2OvDBA1rcmmHHLOaWkEkp4VfTz7U5cCopZulT4CIl8IjQQ-tyS9f1YDnKwuV53zPKVCFel7Yrq5B2FvWetctPZreaEz8zJnIauwqu8HVccNsdMeCE29fuQMXkZrjUf2L8-Dq2QQ25xvdQRndNnE4lNl1zCoelHlVn1V58h2ZKJXriOnxqCulYIj49VH9o-jb5O7WX9uF6xUYpja7rediTtbGrH7F0BKcYGeE8OOjJ5bAXSSO0'
  },
  {
    id: 3,
    name: 'Finca El Cafetal',
    category: 'fincas',
    rating: '5.0',
    tag: 'ECOTURISMO',
    desc: 'Vive la experiencia del café desde su origen en una estancia tradicional y sostenible.',
    location: 'Km 2 Vía Neiva, Rivera',
    phone: '+57 315 444 3322',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCMq8aLmyjnG7wilQLtxWI27We69a4BjB5cMbEgNB0IBek-4_EkcoKq-QFzrDXXDLEosEO9DpgxrTy810umYCPnSEVK5HepEYgmN3FrTEwbf7yRMTWT_ge1aVia11UAnqOYFSEgx1nRBxDDrcobJvKd6DYi7h1NL_6mix9TWlFFsbYJFi-pbw4L6fXqC1Z9MSp4GOZXmr9q3666ouyxcCgfvyb1Vvnx0A-suxDAJ_tdyeMUC1jVekeOQNORtOxB4YE1FP89tL8Qp-o'
  }
]

const gastronomy = [
  {
    id: 4,
    name: 'Ancestros Rivera',
    category: 'restaurantes',
    rating: '4.9',
    tag: 'RECOMENDADO',
    desc: 'El mejor Asado Huilense cocinado lentamente en horno de leña tradicional.',
    location: 'Calle 3 con Carrera 6',
    phone: '+57 321 000 1122',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuBJibDtTszdCsS_CHBn1ycA4q1g51uza3CDuHdEgAiboDxPvkJFSRr_hwl38GduRs1PQDQWb9VHCsjr835fbXV_rEt_saw_BzOdi-gV-1NFakZXUtFykE8dxKzz0E-4IQQWm1SY0lSs-EXLnLomkXBuvk7mkbPPwbU-Rth4J5UeG1gtdBL-4BO93Ku1gzFJlL3_buMfG9XuOUE7L_Xn6bSQCFnrxsAyS3Q9MpJmyE70Xh8iPiGcHUzu5VBO7x8URq7V5re_p_JpzbY'
  },
  {
    id: 5,
    name: 'Delicias de la Abuela',
    category: 'dulcerias',
    rating: '4.8',
    tag: 'DULCES',
    desc: 'Famosas achiras calientes y postres de leche de la tradición opita.',
    location: 'Carrera 4 # 3-12, Centro',
    phone: '+57 311 555 8899',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuBwBs8GvsRjqyLUFYcyVH7zPvd0OdZf506pfNF8bNM9qaCmBC9D0NqfH0DPHXx_-S6YpZ5MiPGCFT9wxquO0EnuuZSrOdOs5tcCN8_t4a89GNBDHk_j6mUbt8MDDSJ1g1cPFFU9s0ZJ5o7VdVygxtu4VyweRrBM-qD38tebJy1J5p0uCewBzCdeewjNa-HcEzchbgMBecOZrSNZ3SuuHCeWCBOnZ-vIC8gl8j5B6FYn2lBDjuIuYD16Boze41PNnPgfYRJ8mIyzWVk'
  }
]

const cafes = [
  {
    id: 6,
    name: 'Café El Mirador',
    category: 'restaurantes',
    desc: 'Disfruta de un café especial con la mejor vista del valle de Rivera.',
    tag: 'Vía Las Termales',
    icon: 'coffee'
  },
  {
    id: 7,
    name: 'Helados de Cholupa',
    category: 'dulcerias',
    desc: 'Sabor exótico del Huila en refrescantes helados artesanales.',
    tag: 'Parque Principal',
    icon: 'icecream'
  }
]

// Search and Filter computation
const filteredAccommodations = computed(() => {
  return accommodations.filter(item => {
    const matchesCategory = selectedCategory.value === 'todos' || item.category === selectedCategory.value
    const matchesSearch = item.name.toLowerCase().includes(searchQuery.value.toLowerCase()) || 
                          item.desc.toLowerCase().includes(searchQuery.value.toLowerCase())
    return matchesCategory && matchesSearch
  })
})

const filteredGastronomy = computed(() => {
  return gastronomy.filter(item => {
    const matchesCategory = selectedCategory.value === 'todos' || item.category === selectedCategory.value
    const matchesSearch = item.name.toLowerCase().includes(searchQuery.value.toLowerCase()) || 
                          item.desc.toLowerCase().includes(searchQuery.value.toLowerCase())
    return matchesCategory && matchesSearch
  })
})

const filteredCafes = computed(() => {
  return cafes.filter(item => {
    const matchesCategory = selectedCategory.value === 'todos' || item.category === selectedCategory.value
    const matchesSearch = item.name.toLowerCase().includes(searchQuery.value.toLowerCase()) || 
                          item.desc.toLowerCase().includes(searchQuery.value.toLowerCase())
    return matchesCategory && matchesSearch
  })
})

const hasActiveFilters = computed(() => {
  return selectedCategory.value !== 'todos' || searchQuery.value.trim() !== ''
})

const hasResults = computed(() => {
  return filteredAccommodations.value.length > 0 || 
         filteredGastronomy.value.length > 0 || 
         filteredCafes.value.length > 0
})

const clearFilters = () => {
  searchQuery.value = ''
  selectedCategory.value = 'todos'
}
</script>

<template>
  <div class="py-12">
    <!-- Hero Search Section -->
    <section class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto mb-16">
      <div class="bg-surface-container-low rounded-xl p-8 md:p-12 relative overflow-hidden shadow-sm">
        <div class="absolute inset-0 opacity-5 pointer-events-none" style="background-image: radial-gradient(#9f4026 1px, transparent 1px); background-size: 20px 20px;"></div>
        <div class="relative z-10 max-w-2xl">
          <h1 class="font-display text-4xl md:text-5xl text-primary mb-4 font-bold">Directorio Local</h1>
          <p class="font-body text-base text-on-surface-variant mb-8 leading-relaxed">
            Descubre los tesoros mejor guardados de Rivera. Desde glampings bajo las estrellas hasta el sabor auténtico de nuestras achiras tradicionales y cafés especiales.
          </p>
          <!-- Search Engine -->
          <div class="bg-white p-2 rounded-full shadow-lg flex items-center gap-2 border border-outline-variant">
            <span class="material-symbols-outlined ml-4 text-on-surface-variant">search</span>
            <input 
              v-model="searchQuery"
              class="w-full border-none focus:ring-0 bg-transparent text-sm py-2 focus:outline-none" 
              placeholder="¿Qué estás buscando hoy? (Ej: achiras, glamping, café)" 
              type="text"
            />
            <button class="bg-secondary text-on-secondary px-6 py-3 rounded-full font-bold text-xs hover:bg-secondary-container transition-all whitespace-nowrap">
              Buscar
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Category Filters -->
    <section class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto mb-12">
      <div class="flex gap-4 overflow-x-auto no-scrollbar pb-2">
        <button 
          v-for="cat in categories"
          :key="cat.id"
          @click="selectedCategory = cat.id"
          class="px-6 py-2.5 rounded-full flex items-center gap-2 font-semibold text-xs whitespace-nowrap transition-all"
          :class="selectedCategory === cat.id 
            ? 'bg-primary text-on-primary shadow-md' 
            : 'bg-surface-container-high text-on-surface-variant hover:bg-surface-variant'"
        >
          <span class="material-symbols-outlined text-base">{{ cat.icon }}</span> 
          {{ cat.label }}
        </button>
      </div>
    </section>

    <!-- Search Results / Directory Sections -->
    <div class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
      
      <!-- No Results State -->
      <div v-if="!hasResults" class="text-center py-16 bg-surface-container-low rounded-2xl border border-outline-variant/40">
        <span class="material-symbols-outlined text-6xl text-outline mb-4">search_off</span>
        <h3 class="font-display text-xl font-bold text-primary mb-2">No se encontraron resultados</h3>
        <p class="text-on-surface-variant text-sm mb-6">Prueba a buscar con otras palabras clave o limpia los filtros.</p>
        <button @click="clearFilters" class="bg-secondary text-on-secondary px-6 py-2.5 rounded-full font-bold text-xs hover:bg-secondary-container transition-all">
          Limpiar Filtros
        </button>
      </div>

      <!-- General View: Filtered Results (when search is active) -->
      <div v-else-if="hasActiveFilters">
        <div class="flex justify-between items-center mb-8 pb-4 border-b border-outline-variant/30">
          <h2 class="font-display text-2xl text-primary font-bold">Resultados Filtrados</h2>
          <button @click="clearFilters" class="text-secondary font-bold text-xs flex items-center gap-1 hover:underline">
            Limpiar Filtros <span class="material-symbols-outlined text-xs">close</span>
          </button>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-gutter">
          <!-- Render Accommodations -->
          <div 
            v-for="item in filteredAccommodations" 
            :key="'acc-'+item.id"
            class="group bg-white rounded-xl overflow-hidden shadow-md border border-outline-variant hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex flex-col"
          >
            <div class="h-56 overflow-hidden relative">
              <img :alt="item.name" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" :src="item.img" />
              <div class="absolute top-4 left-4 bg-tertiary text-on-tertiary px-3 py-1 rounded-full text-[10px] font-bold tracking-wider">{{ item.tag }}</div>
            </div>
            <div class="p-6 flex-grow flex flex-col justify-between">
              <div>
                <div class="flex justify-between items-start mb-2">
                  <h3 class="font-display text-lg text-on-surface font-bold">{{ item.name }}</h3>
                  <div class="flex items-center text-tertiary">
                    <span class="material-symbols-outlined text-base" style="font-variation-settings: 'FILL' 1;">star</span>
                    <span class="text-xs font-bold ml-1">{{ item.rating }}</span>
                  </div>
                </div>
                <p class="text-on-surface-variant text-sm mb-6 leading-relaxed">{{ item.desc }}</p>
              </div>
              <div class="flex flex-col gap-2 pt-4 border-t border-outline-variant/30 text-xs text-on-surface-variant font-medium">
                <div class="flex items-center gap-2"><span class="material-symbols-outlined text-secondary text-sm">location_on</span> {{ item.location }}</div>
                <div class="flex items-center gap-2"><span class="material-symbols-outlined text-secondary text-sm">call</span> {{ item.phone }}</div>
              </div>
            </div>
          </div>

          <!-- Render Gastronomy -->
          <div 
            v-for="item in filteredGastronomy" 
            :key="'gast-'+item.id"
            class="group bg-white rounded-xl overflow-hidden shadow-md border border-outline-variant hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex flex-col"
          >
            <div class="h-56 overflow-hidden relative">
              <img :alt="item.name" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" :src="item.img" />
              <div class="absolute top-4 left-4 bg-secondary text-on-secondary px-3 py-1 rounded-full text-[10px] font-bold tracking-wider">{{ item.tag }}</div>
            </div>
            <div class="p-6 flex-grow flex flex-col justify-between">
              <div>
                <div class="flex justify-between items-start mb-2">
                  <h3 class="font-display text-lg text-on-surface font-bold">{{ item.name }}</h3>
                  <div class="flex items-center text-tertiary">
                    <span class="material-symbols-outlined text-base" style="font-variation-settings: 'FILL' 1;">star</span>
                    <span class="text-xs font-bold ml-1">{{ item.rating }}</span>
                  </div>
                </div>
                <p class="text-on-surface-variant text-sm mb-6 leading-relaxed">{{ item.desc }}</p>
              </div>
              <div class="flex flex-col gap-2 pt-4 border-t border-outline-variant/30 text-xs text-on-surface-variant font-medium">
                <div class="flex items-center gap-2"><span class="material-symbols-outlined text-secondary text-sm">location_on</span> {{ item.location }}</div>
                <div class="flex items-center gap-2"><span class="material-symbols-outlined text-secondary text-sm">call</span> {{ item.phone }}</div>
              </div>
            </div>
          </div>

          <!-- Render Cafes -->
          <div 
            v-for="item in filteredCafes" 
            :key="'cafe-'+item.id"
            class="group bg-surface-container rounded-xl p-6 flex flex-col justify-between border border-outline-variant hover:bg-primary-container hover:text-white transition-all shadow-sm"
          >
            <div>
              <span class="material-symbols-outlined text-secondary group-hover:text-on-primary-container text-4xl mb-4">{{ item.icon }}</span>
              <h4 class="font-display text-lg mb-2 font-bold">{{ item.name }}</h4>
              <p class="text-sm opacity-80 mb-6 leading-relaxed">{{ item.desc }}</p>
            </div>
            <span class="text-[10px] font-bold uppercase tracking-wider block pt-2 border-t border-outline-variant/30">{{ item.tag }}</span>
          </div>
        </div>
      </div>

      <!-- Standard Layout: Sections (when no filters are active) -->
      <div v-else>
        <!-- Section: Accommodations -->
        <section class="mb-20">
          <div class="flex justify-between items-end mb-8">
            <div>
              <span class="text-secondary font-bold text-xs uppercase tracking-widest block mb-2">Refugios & Descanso</span>
              <h2 class="font-display text-2xl md:text-3xl text-primary font-bold">Dónde Quedarse</h2>
            </div>
            <button @click="selectedCategory = 'glampings'" class="text-primary font-bold text-xs flex items-center gap-1 hover:underline">
              Ver Glampings <span class="material-symbols-outlined text-xs">arrow_forward</span>
            </button>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-gutter">
            <div 
              v-for="item in filteredAccommodations" 
              :key="'acc-sec-'+item.id"
              class="group bg-white rounded-xl overflow-hidden shadow-md border border-outline-variant hover:shadow-xl transition-all duration-300 transform hover:-translate-y-1 flex flex-col"
            >
              <div class="h-64 overflow-hidden relative">
                <img :alt="item.name" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" :src="item.img" />
                <div class="absolute top-4 left-4 bg-tertiary text-on-tertiary px-3 py-1 rounded-full text-[10px] font-bold tracking-wider">{{ item.tag }}</div>
              </div>
              <div class="p-6 flex-grow flex flex-col justify-between">
                <div>
                  <div class="flex justify-between items-start mb-2">
                    <h3 class="font-display text-lg text-on-surface font-bold">{{ item.name }}</h3>
                    <div class="flex items-center text-tertiary">
                      <span class="material-symbols-outlined text-base" style="font-variation-settings: 'FILL' 1;">star</span>
                      <span class="text-xs font-bold ml-1">{{ item.rating }}</span>
                    </div>
                  </div>
                  <p class="text-on-surface-variant text-sm mb-6 leading-relaxed">{{ item.desc }}</p>
                </div>
                <div class="flex flex-col gap-2 pt-4 border-t border-outline-variant/30 text-xs text-on-surface-variant font-medium">
                  <div class="flex items-center gap-2"><span class="material-symbols-outlined text-secondary text-sm">location_on</span> {{ item.location }}</div>
                  <div class="flex items-center gap-2"><span class="material-symbols-outlined text-secondary text-sm">call</span> {{ item.phone }}</div>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- Section: Gastronomy -->
        <section class="mb-20">
          <div class="flex justify-between items-end mb-8">
            <div>
              <span class="text-secondary font-bold text-xs uppercase tracking-widest block mb-2">Sabor del Huila</span>
              <h2 class="font-display text-2xl md:text-3xl text-primary font-bold">Dónde Comer</h2>
            </div>
            <button @click="selectedCategory = 'restaurantes'" class="text-primary font-bold text-xs flex items-center gap-1 hover:underline">
              Ver Restaurantes <span class="material-symbols-outlined text-xs">arrow_forward</span>
            </button>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-12 gap-gutter">
            <!-- Featured Restaurant (Big) -->
            <div class="md:col-span-8 group relative overflow-hidden rounded-xl shadow-lg h-[400px]">
              <img 
                alt="Restaurante Típico" 
                class="w-full h-full object-cover group-hover:scale-103 transition-transform duration-700" 
                src="https://lh3.googleusercontent.com/aida-public/AB6AXuBJibDtTszdCsS_CHBn1ycA4q1g51uza3CDuHdEgAiboDxPvkJFSRr_hwl38GduRs1PQDQWb9VHCsjr835fbXV_rEt_saw_BzOdi-gV-1NFakZXUtFykE8dxKzz0E-4IQQWm1SY0lSs-EXLnLomkXBuvk7mkbPPwbU-Rth4J5UeG1gtdBL-4BO93Ku1gzFJlL3_buMfG9XuOUE7L_Xn6bSQCFnrxsAyS3Q9MpJmyE70Xh8iPiGcHUzu5VBO7x8URq7V5re_p_JpzbY"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-primary/95 via-primary/30 to-transparent p-8 flex flex-col justify-end">
                <div class="bg-secondary-container text-on-secondary-container w-fit px-3 py-1 rounded-full text-xs font-bold mb-4">RECOMENDADO</div>
                <h3 class="font-display text-2xl md:text-3xl text-white mb-2 font-bold">Ancestros Rivera</h3>
                <p class="text-on-primary-container text-sm mb-4 line-clamp-2 max-w-lg">El mejor Asado Huilense cocinado lentamente en horno de leña tradicional, siguiendo recetas centenarias.</p>
                <div class="flex flex-wrap gap-6 text-white text-xs font-bold">
                  <span class="flex items-center gap-2"><span class="material-symbols-outlined text-sm">call</span> +57 321 000 1122</span>
                  <span class="flex items-center gap-2"><span class="material-symbols-outlined text-sm">map</span> Calle 3 con Carrera 6, Centro</span>
                </div>
              </div>
            </div>

            <!-- Traditional Sweets (Medium) -->
            <div class="md:col-span-4 group relative overflow-hidden rounded-xl shadow-md h-[400px]">
              <img 
                alt="Achiras Tradicionales" 
                class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500" 
                src="https://lh3.googleusercontent.com/aida-public/AB6AXuBwBs8GvsRjqyLUFYcyVH7zPvd0OdZf506pfNF8bNM9qaCmBC9D0NqfH0DPHXx_-S6YpZ5MiPGCFT9wxquO0EnuuZSrOdOs5tcCN8_t4a89GNBDHk_j6mUbt8MDDSJ1g1cPFFU9s0ZJ5o7VdVygxtu4VyweRrBM-qD38tebJy1J5p0uCewBzCdeewjNa-HcEzchbgMBecOZrSNZ3SuuHCeWCBOnZ-vIC8gl8j5B6FYn2lBDjuIuYD16Boze41PNnPgfYRJ8mIyzWVk"
              />
              <div class="absolute inset-0 bg-black/45 group-hover:bg-black/25 transition-all p-6 flex flex-col justify-end text-white">
                <h3 class="font-display text-xl mb-1 font-bold">Delicias de la Abuela</h3>
                <p class="text-white/80 text-xs font-semibold">Famosas achiras calientes y postres de cuajada.</p>
              </div>
            </div>

            <!-- Small Grid Item 1 -->
            <div 
              v-for="item in filteredCafes"
              :key="'cafe-sec-'+item.id"
              class="md:col-span-6 group bg-surface-container rounded-xl p-8 flex flex-col justify-between border border-outline-variant hover:bg-primary-container hover:text-white transition-all shadow-sm"
            >
              <div>
                <span class="material-symbols-outlined text-secondary group-hover:text-on-primary-container text-4xl mb-4">{{ item.icon }}</span>
                <h4 class="font-display text-xl mb-2 font-bold">{{ item.name }}</h4>
                <p class="text-sm opacity-80 mb-6 leading-relaxed">{{ item.desc }}</p>
              </div>
              <span class="text-[10px] font-bold uppercase tracking-wider block pt-2 border-t border-outline-variant/30">{{ item.tag }}</span>
            </div>
          </div>
        </section>
      </div>

    </div>

    <!-- Register CTA -->
    <section class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto my-16">
      <div class="bg-primary-container rounded-2xl p-10 md:p-16 text-center text-on-primary-container relative overflow-hidden shadow-lg">
        <div class="absolute -right-20 -top-20 w-64 h-64 bg-surface-tint opacity-20 rounded-full blur-3xl"></div>
        <div class="absolute -left-20 -bottom-20 w-64 h-64 bg-secondary opacity-20 rounded-full blur-3xl"></div>
        <h2 class="font-display text-2xl md:text-3xl text-white mb-6 font-bold">¿Quieres aparecer aquí?</h2>
        <p class="font-body text-base text-primary-fixed mb-10 max-w-xl mx-auto leading-relaxed">
          Únete a nuestra red de prestadores turísticos formales y muestra lo mejor de tu negocio a miles de visitantes nacionales y extranjeros.
        </p>
        <button class="bg-white text-primary px-10 py-4 rounded-full font-bold text-sm hover:shadow-2xl transition-all hover:-translate-y-1">
          Registrar mi Negocio
        </button>
      </div>
    </section>
  </div>
</template>
