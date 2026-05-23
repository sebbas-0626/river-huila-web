<script setup>
import { ref } from 'vue'

useSeoMeta({
  title: 'Lugares qué visitar - Rivera Huila',
  description: 'Explora los mejores destinos turísticos en Rivera, Huila. Desde los termales medicinales hasta los viñedos de La Ulloa.'
})

const activeCategory = ref('todos')

const categories = [
  { id: 'todos', label: 'Todos los Lugares' },
  { id: 'bienestar', label: 'Bienestar y Termalismo' },
  { id: 'ecoturismo', label: 'Ecoturismo e Historia' },
  { id: 'vino', label: 'Vino y Arte' },
  { id: 'arquitectura', label: 'Arquitectura y Legado' }
]
</script>

<template>
  <div class="py-12 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
    <!-- Header Section -->
    <header class="mb-12">
      <h1 class="font-display text-4xl md:text-5xl text-primary mb-4 font-bold">Descubre Rivera</h1>
      <p class="font-body text-base md:text-lg text-on-surface-variant max-w-2xl leading-relaxed">
        Un refugio donde las aguas termales sanan el cuerpo y los senderos coloniales cuentan historias de un pasado eterno. Explora nuestros atractivos turísticos seleccionados.
      </p>
    </header>

    <!-- Category Filters -->
    <div class="flex flex-wrap gap-3 mb-12 overflow-x-auto pb-4 no-scrollbar">
      <button 
        v-for="cat in categories" 
        :key="cat.id"
        @click="activeCategory = cat.id"
        class="px-5 py-2.5 rounded-full border border-outline-variant font-semibold text-xs transition-all whitespace-nowrap"
        :class="activeCategory === cat.id 
          ? 'bg-primary text-on-primary border-primary shadow-md' 
          : 'bg-surface text-on-surface-variant hover:bg-surface-container-high'"
      >
        {{ cat.label }}
      </button>
    </div>

    <!-- Bento Grid of Places -->
    <div class="grid grid-cols-1 md:grid-cols-12 gap-gutter">
      
      <!-- Big Feature Card: Termales -->
      <div 
        v-show="activeCategory === 'todos' || activeCategory === 'bienestar'"
        class="md:col-span-8 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl hover:-translate-y-1 h-[400px] md:h-[450px]"
      >
        <img 
          alt="Termales de Rivera" 
          class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
          src="https://lh3.googleusercontent.com/aida-public/AB6AXuBnOnMWyb9MtgvFtNf91TAzcrq_CupctI5EE1xebUY4tp7ZMqbeZMeYYKKcCj6heBo_I3u-h5EmMMH8qusnO_B4GrmIKUnRkz0UN9m-JLf_1_b7jY3cAUZFHX9txuZ0I127-fyt3_rqv9xhLTFt1_VHKCRnZi_H9u8Ak5r7lvNcjhBE7QpOjia240hZiMHzxlZNuvu5vT52TWThvjL2cmUUD1vQWw7X9P4KMpWeTQiWLIhFIy6VH8FMYpVNQC5rqwR-jHebiVdJ894"
        />
        <div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/25 to-transparent"></div>
        <div class="absolute bottom-0 left-0 p-8 text-white">
          <span class="bg-tertiary text-on-tertiary px-3 py-1 rounded-full text-xs font-bold mb-4 inline-block tracking-wider">BIENESTAR</span>
          <h3 class="font-display text-2xl md:text-3xl font-bold mb-2">Termales de Rivera</h3>
          <p class="text-white/80 text-sm max-w-lg mb-6 leading-relaxed">
            Aguas medicinales termales que brotan del corazón de la cordillera, rodeadas de un bosque tropical húmedo y tranquilidad absoluta.
          </p>
          <NuxtLink to="/planifica" class="flex items-center gap-2 font-semibold text-xs hover:underline">
            Explorar experiencia 
            <span class="material-symbols-outlined text-sm">arrow_forward</span>
          </NuxtLink>
        </div>
      </div>

      <!-- Side Card: Cascada -->
      <div 
        v-show="activeCategory === 'todos' || activeCategory === 'ecoturismo'"
        class="md:col-span-4 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl hover:-translate-y-1 bg-surface-container flex flex-col h-[400px] md:h-[450px]"
      >
        <div class="h-1/2 overflow-hidden">
          <img 
            alt="Salto del Ángel" 
            class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuCw3S92Q5kCF236bcSrptr3lgvzT4wz_sSZlxzz4x4R9Vd5JEvZD_oUeu6Ua_M_Lyvzh8dwB9m42NqdJwd-dd77W9MPoNgeKk4WH4jJVmKGj6gMK-aaQQByzX-x_DbJlRbNnGHwWmYZQTUVnR1ihVR7ufKSeGqMjCFpxCnfEW1GH0fJdjoL3Grlb0LjmmFfzdz0RD971RHWHwc2iCDohqBkzWOn8JYSO6zYJUMziAy721P6Q2vGAja3tWxz9G3OC0HvcbjqDn9eV60"
          />
        </div>
        <div class="p-6 flex-grow flex flex-col justify-center">
          <span class="text-primary font-bold text-xs mb-2 block tracking-wider">ECOTURISMO</span>
          <h4 class="font-display text-lg md:text-xl text-primary mb-2 font-bold">Cascada Salto del Ángel</h4>
          <p class="text-on-surface-variant text-sm line-clamp-2 leading-relaxed">
            Una caída de agua de 80 metros escondida en la selva andina, ideal para senderistas.
          </p>
        </div>
      </div>

      <!-- Row 2: Vinos y Murales -->
      <div 
        v-show="activeCategory === 'todos' || activeCategory === 'vino'"
        class="md:col-span-4 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl hover:-translate-y-1 bg-surface-container flex flex-col h-[400px]"
      >
        <div class="h-1/2 overflow-hidden">
          <img 
            alt="Murales de La Ulloa" 
            class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuAkW0hMvUYGOxgels8LE95WKAPI8GRgFMXpqmEG8mk1sHnhwAiZmIk7qUf4pA2dqi22u2oxjA1PtmTFohjz1SeMDc4BNz4rAbjR-vXhJ2AFcKL-pVq1zHAepPj4_f5cW4_8ESRCP8moDI2g14UKAUPQRpM0d_aoF4YznMB9qQY2C4dKltwz6UQU-MVUQHHE1vHsu7-gNn4EOIPsw4DU4S0-JWCuq3ni_jtmBPjCvf9Po-_DQFLJEApPpwGOy5hiiBYfebxkZgq7Lc4"
          />
        </div>
        <div class="p-6 flex-grow flex flex-col justify-center">
          <span class="text-secondary font-bold text-xs mb-2 block tracking-wider">ARTE Y SABOR</span>
          <h4 class="font-display text-lg md:text-xl text-primary mb-2 font-bold">La Ulloa: Murales y Vino</h4>
          <p class="text-on-surface-variant text-sm line-clamp-2 leading-relaxed">
            Calles empedradas con murales artísticos y cata de vino de uva y frutas regionales.
          </p>
        </div>
      </div>

      <!-- Row 2: Templo Parroquial -->
      <div 
        v-show="activeCategory === 'todos' || activeCategory === 'arquitectura'"
        class="md:col-span-8 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl hover:-translate-y-1 h-[400px]"
      >
        <div class="grid grid-cols-1 md:grid-cols-2 h-full">
          <div class="relative overflow-hidden h-1/2 md:h-full">
            <img 
              alt="Templo Parroquial" 
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuBzrjcDOm0CGzOsPuXW0GMJrKBWFPFqbQLxv2Q0Qy4WoTIeEleSPTywxU8x0cliX5g1tDq_DrM3zup_KcMCTj11qyDkGYxO-W1Ho5lpN-dBM-5ACMgi777VYc8QrDN_SYq_eoKKOtWrLLZgEUWUx5-KJWdVq5ETZGVyoEZs1RISu3fdH-OrhuDGS8UgmHR-LSlT0-5NnjYzGBQSlvPNxhicYAdNaBiAevu3hXTb9Qik4zn0vPf8Uz9cR_7nvs1JRawajj2s3J9RomA"
            />
          </div>
          <div class="bg-primary text-white p-8 flex flex-col justify-center h-1/2 md:h-full">
            <span class="bg-secondary/20 text-secondary-fixed border border-secondary px-3 py-1 rounded-full text-xs font-bold mb-4 w-fit tracking-wider">ARQUITECTURA</span>
            <h4 class="font-display text-xl md:text-2xl mb-4 font-bold">Templo Perpetuo Socorro</h4>
            <p class="text-white/85 text-xs md:text-sm mb-6 leading-relaxed">
              Un hito colonial frente al parque central que preserva vitrales y maderas nobles.
            </p>
            <div class="flex flex-wrap gap-4 text-xs">
              <div class="flex items-center gap-1 font-semibold"><span class="material-symbols-outlined text-sm">schedule</span> 07:00 - 18:00</div>
              <div class="flex items-center gap-1 font-semibold"><span class="material-symbols-outlined text-sm">location_on</span> Parque Central</div>
            </div>
          </div>
        </div>
      </div>

      <!-- Row 3: Senderos -->
      <div 
        v-show="activeCategory === 'todos' || activeCategory === 'ecoturismo'"
        class="md:col-span-6 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl hover:-translate-y-1 bg-surface-container flex flex-col"
      >
        <div class="aspect-[16/9] w-full overflow-hidden">
          <img 
            alt="Senderos de Rivera" 
            class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuCO5LvVQS2NWMdFATd2bZtOaaQhPBdGNx34NdCWQ5loGSIv9F3VjN9e6wgLCDbtCNxRlZYzuHAjO6oCOv2YnsAZN_iIOgbPaKwENhWvKeTAnjoTJEhbRl29dwoRoS2FbBcWCZXrtbR8osyP9yizUgGc0Du7ILi-pnJ3a0HlFaVQwDdtX5YKHLXUQ4yetDahUgvUP70no_TvSW8UcFG5p0RYKwnL8llrAf492loKyliXH73k70uUkDtfut2UdciDhUmnLWOO6Pfch-g"
          />
        </div>
        <div class="p-8">
          <div class="flex justify-between items-start mb-4">
            <span class="text-primary font-bold text-xs tracking-wider">HISTORIA NATURAL</span>
            <div class="flex text-secondary">
              <span class="material-symbols-outlined text-sm" style="font-variation-settings: 'FILL' 1;">star</span>
              <span class="material-symbols-outlined text-sm" style="font-variation-settings: 'FILL' 1;">star</span>
              <span class="material-symbols-outlined text-sm" style="font-variation-settings: 'FILL' 1;">star</span>
              <span class="material-symbols-outlined text-sm" style="font-variation-settings: 'FILL' 1;">star</span>
              <span class="material-symbols-outlined text-sm">star_half</span>
            </div>
          </div>
          <h4 class="font-display text-xl text-primary mb-2 font-bold">Sendero Los Arrayanes</h4>
          <p class="text-on-surface-variant text-sm mb-6 leading-relaxed">
            Camino ecológico ancestral que bordea quebradas naturales, propicio para el avistamiento de avifauna.
          </p>
          <NuxtLink to="/planifica" class="bg-outline-variant/60 text-on-surface px-6 py-2 rounded-full font-bold text-xs hover:bg-primary hover:text-on-primary transition-all">
            Ver mapa de ruta
          </NuxtLink>
        </div>
      </div>

      <!-- Row 3: Parque Principal -->
      <div 
        v-show="activeCategory === 'todos' || activeCategory === 'arquitectura'"
        class="md:col-span-6 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl hover:-translate-y-1 bg-surface-container flex flex-col"
      >
        <div class="aspect-[16/9] w-full overflow-hidden">
          <img 
            alt="Parque Principal" 
            class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuC4Xf6abSou6iPYQI67vHOmVc4ALV2HY-o9SwK_gkPJeBt-DsZTTHn8Ny9dEW9GcZDLCLDrMi5iD37nsyZ9XNgYffZhCqdDM64IQ-pybD6qinZ5b_5tZor5cz2iTYGTbVM1Xgf5jXbXIwHMlkdfLZ0uEix9pTLHqx1m9jZzDTw7Yyqk3h15j-cRAlN4dWqiXIeFsnRg9MKMuB33y53rrkdJFbM-Yl79PpJ1b3oOPeTnxeC4wlARjp444kQmKGn_lEJO2O-cXO3gDEc"
          />
        </div>
        <div class="p-8">
          <span class="text-secondary font-bold text-xs mb-2 block tracking-wider">LEGADO VIVO</span>
          <h4 class="font-display text-xl text-primary mb-2 font-bold">Parque Principal de Rivera</h4>
          <p class="text-on-surface-variant text-sm mb-6 leading-relaxed">
            Plaza arbolada famosa por sus ceibas gigantes, rodeada de cafés tradicionales y heladerías de cholupa.
          </p>
          <div class="flex items-center gap-4 text-primary text-xs">
            <div class="flex items-center gap-1 font-bold"><span class="material-symbols-outlined text-sm">camera</span> Zona de fotos</div>
            <div class="flex items-center gap-1 font-bold"><span class="material-symbols-outlined text-sm">coffee</span> Cafés de origen</div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>
