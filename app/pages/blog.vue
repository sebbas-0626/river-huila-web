<script setup>
import { ref, computed } from 'vue'

useSeoMeta({
  title: 'Blog e Historias - Rivera Huila',
  description: 'Descubre las crónicas, leyendas y guías sobre Rivera de la mano de escritores e historiadores locales.'
})

// ── Datos de artículos ────────────────────────────────────────────────────────
const allArticles = [
  {
    id: 1,
    category: 'Artesanía',
    categoryColor: 'bg-primary-container text-on-primary-container',
    readTime: '8 MIN',
    title: 'Detrás del Plan Fachada: Artesanos y colores',
    excerpt: 'En el corazón de Rivera, un grupo de manos maestras ha decidido que las paredes deben contar historias. Es una restauración de identidad colonial con pigmentos de la tierra arcillosa.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuD6TnPxDI8NZh63OKRJ364KW9BTdEERSImEi_n7ws87XCI7I0rVNOX9Gu51hfitTDt4MB8D3Phqc5Ls9zgXgRBgO4O_wP5ICF4xMrw9UEsMtPzX9dpoOvFFWExl5AA0vvFcAgf6A039exTd_FBcGcHPO64bv-_KqN87NMWDwaJko8r2pf3aZpXbtRVX-ReRC2HGQASYVqr4-WHaWikaxz3NioEmednesa2-NTG5KJrkdyVs6WbxGvCXolBYxsuna0Ocal_RF4icn2c',
    cta: 'LEER CRÓNICA',
    featured: true
  },
  {
    id: 2,
    category: 'Gastronomía',
    categoryColor: 'bg-tertiary/15 text-tertiary',
    readTime: '5 MIN',
    title: 'Ruta del Vino en La Ulloa',
    excerpt: 'Entre vides y brisa de montaña, La Ulloa se ha convertido en el santuario del enoturismo en el Huila. Un recorrido sensorial por cavas familiares y bodegas artesanales.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAiV7QY-vmDUnEHWjlVFEY5LZ78-RasRaXR7F0HKjMajPVJlzoedIawINliXATCby3L0Fhh7yexhKuM8_55vv7CsCQGbjBa1-zaPzqN8ABM3Ovatz48xkIqeefYFbUfWpBzw4vMCoHuaeRKMqgESKwg3wJz_RAd_DIWT9Ob79kcF6I18bZ0Lv_OO6bLHW79RRnqhAooAhjIYQI3a4FCar6PXFbxImasNVvZLut30kTMVAH_9PdSZcWkXyRaMAGF79lGnvyefSpqmJg',
    cta: 'DESCUBRIR RUTA',
    featured: false
  },
  {
    id: 3,
    category: 'Cultura',
    categoryColor: 'bg-secondary/15 text-secondary',
    readTime: '12 MIN',
    title: 'La Vorágine y el legado de José Eustasio Rivera',
    excerpt: 'Un centenario después, la pluma de nuestro hijo ilustre sigue vibrando. Un análisis sobre cómo la selva de Rivera se convirtió en poesía y denuncia social.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCCn-DVoSXzDAhle9pVJ3f-G_2fR_xL2Ex9Z5BCk2vqF2EZwgN4Ir3GTOoXxif01drJNlo971jUoFcuUetrTvjZ0AIOnW6hdOACfy1hg1qaxunv2QwzISOJGBChD2_kBry1za-yoL3QwV73C56iCGARm3ktEU_vEPNOXz5gusfXUnleAz4co2JOqsxiNWbB5iBIaHTyj2OVgmeRZzAs9uilIJzlpxwT0csJPldSDi86k4WGqmH54-VRFL7fOO-BFmbFRNF54y9byxU',
    cta: 'EXPLORAR LEGADO',
    featured: false
  },
  {
    id: 4,
    category: 'Ecoturismo',
    categoryColor: 'bg-primary/15 text-primary',
    readTime: '6 MIN',
    title: 'Noche bajo las estrellas en las termales',
    excerpt: 'Cuando el sol se oculta tras los cerros, las termales cobran vida mística. Guía completa para planificar la experiencia nocturna definitiva: astronomía, relax y más.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCwakcNf2Jdoqaem3hbXjyzTS1K7nPAXhs3Od0tHRGNz89F6AH1z_A4J-JtlVlLQNnpxWQGNj_yluzW1Wc3IfsAik9EuLWPLKpBKd-YH6q73b0ci8icoUq9IVLoHsre2KgCeqw42KcdKBMrHrBjKCMC1K5KMHoXn0qrfLatbBYsfx8-rzhZQnTYMGbUaxlm8xLz3HZK_8fl7M9PBZVGv6yDABloZuljf0Q7KwOqCg87NtAAhfaouAI0vDBX4xs6v1cx_PgWz5I_wRE',
    cta: 'LEER GUÍA',
    featured: false
  },
  {
    id: 5,
    category: 'Historia',
    categoryColor: 'bg-primary-container text-on-primary-container',
    readTime: '10 MIN',
    title: 'El Parque Principal: alma y corazón de Rivera',
    excerpt: 'Las ceibas centenarias del parque han sido testigos mudos de la historia del municipio. Desde la fundación colonial hasta los alegres festivales del Sanjuanero Huilense.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuC4Xf6abSou6iPYQI67vHOmVc4ALV2HY-o9SwK_gkPJeBt-DsZTTHn8Ny9dEW9GcZDLCLDrMi5iD37nsyZ9XNgYffZhCqdDM64IQ-pybD6qinZ5b_5tZor5cz2iTYGTbVM1Xgf5jXbXIwHMlkdfLZ0uEix9pTLHqx1m9jZzDTw7Yyqk3h15j-cRAlN4dWqiXIeFsnRg9MKMuB33y53rrkdJFbM-Yl79PpJ1b3oOPeTnxeC4wlARjp444kQmKGn_lEJO2O-cXO3gDEc',
    cta: 'LEER HISTORIA',
    featured: false
  },
  {
    id: 6,
    category: 'Aventura',
    categoryColor: 'bg-tertiary/15 text-tertiary',
    readTime: '7 MIN',
    title: 'Sendero Los Arrayanes: guía para avistamiento de aves',
    excerpt: 'Más de 250 especies de aves habitan los bosques de galería de Los Arrayanes. Esta guía te dice cuándo ir, qué llevar y cuáles son las joyas ornitológicas del sendero.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCO5LvVQS2NWMdFATd2bZtOaaQhPBdGNx34NdCWQ5loGSIv9F3VjN9e6wgLCDbtCNxRlZYzuHAjO6oCOv2YnsAZN_iIOgbPaKwENhWvKeTAnjoTJEhbRl29dwoRoS2FbBcWCZXrtbR8osyP9yizUgGc0Du7ILi-pnJ3a0HlFaVQwDdtX5YKHLXUQ4yetDahUgvUP70no_TvSW8UcFG5p0RYKwnL8llrAf492loKyliXH73k70uUkDtfut2UdciDhUmnLWOO6Pfch-g',
    cta: 'VER GUÍA',
    featured: false
  },
  {
    id: 7,
    category: 'Cultura',
    categoryColor: 'bg-secondary/15 text-secondary',
    readTime: '9 MIN',
    title: 'Festival del Retorno: cuando Rivera se viste de fiesta',
    excerpt: 'Cada junio, el corazón de Rivera late al ritmo del Sanjuanero Huilense. Crónica de la celebración más importante del municipio, sus trajes, su música y su tradición.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAAE2bIxozoLSpKbZdini3nPv2kNuFmeWw6o_mNrGgArkmP3IoGTmgEpYk8OsII9l9hpS2ZZc4zyx9rqVZg71afUZF7cPLvpSgPF_AIqlNqycWtBz7RZqgDwqFKbKcP4feFRnHxzTpA140lZZE1yEjxmzHh7zMb7aVbUE1grB-Z3-ejngDBCgOsmrb5ntp6udiGTRsUUgp9o1bNNMCaFovT-3LKATb8u7dW0RJZETn2huSQ4zFijGRrqZK6NlXJy4dUzdFHYhL8YAs',
    cta: 'LEER CRÓNICA',
    featured: false
  },
  {
    id: 8,
    category: 'Gastronomía',
    categoryColor: 'bg-tertiary/15 text-tertiary',
    readTime: '4 MIN',
    title: 'Achiras de Rivera: el bocado de bienvenida',
    excerpt: 'El bizcocho de achira es el embajador gastronómico de Rivera en el mundo. Historia, receta y los mejores sitios para encontrar los más crujientes y calientes.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuCP2S9EUZc64pbi6M4wDNJoNCvZHzklwaqPGU00RkUCD8UZ1kY4Cyn-ZKryGX6i0HdNZfJki1IHHCxbCG81PS3y3rGr1vxYu5R828dsYwjaO8ko9Aw0DVNBfs6Xf1nfdx73Gd2-vJo7wXg7gx7xSbJaZGOaA_7nnYBDOdbCVrZSrrtC3fk0wMddGiXyO1P3eV87BKOV2dubnNP13NBlXd2qUMdnXqv_rNyoT2OCdng73rAlbqpcZgDM-yjoJH6wBvGyQSTThkeo25A',
    cta: 'LEER MÁS',
    featured: false
  },
  {
    id: 9,
    category: 'Arquitectura',
    categoryColor: 'bg-primary/15 text-primary',
    readTime: '11 MIN',
    title: 'El Templo del Perpetuo Socorro: 200 años de fe',
    excerpt: 'Los vitrales originales y las maderas nobles de la iglesia colonial son una cápsula del tiempo. Recorrido histórico por la joya arquitectónica del Parque Principal de Rivera.',
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuBzrjcDOm0CGzOsPuXW0GMJrKBWFPFqbQLxv2Q0Qy4WoTIeEleSPTywxU8x0cliX5g1tDq_DrM3zup_KcMCTj11qyDkGYxO-W1Ho5lpN-dBM-5ACMgi777VYc8QrDN_SYq_eoKKOtWrLLZgEUWUx5-KJWdVq5ETZGVyoEZs1RISu3fdH-OrhuDGS8UgmHR-LSlT0-5NnjYzGBQSlvPNxhicYAdNaBiAevu3hXTb9Qik4zn0vPf8Uz9cR_7nvs1JRawajj2s3J9RomA',
    cta: 'EXPLORAR',
    featured: false
  }
]

// ── Paginación ────────────────────────────────────────────────────────────────
const ARTICLES_PER_PAGE = 4
const currentPage = ref(1)

const totalPages = computed(() => Math.ceil(allArticles.length / ARTICLES_PER_PAGE))

const paginatedArticles = computed(() => {
  const start = (currentPage.value - 1) * ARTICLES_PER_PAGE
  return allArticles.slice(start, start + ARTICLES_PER_PAGE)
})

// Números de páginas visibles (máx 5, con elipsis automática)
const visiblePages = computed(() => {
  const pages = []
  const total = totalPages.value
  const current = currentPage.value
  if (total <= 5) {
    for (let i = 1; i <= total; i++) pages.push(i)
  } else {
    pages.push(1)
    if (current > 3) pages.push('...')
    for (let i = Math.max(2, current - 1); i <= Math.min(total - 1, current + 1); i++) {
      pages.push(i)
    }
    if (current < total - 2) pages.push('...')
    pages.push(total)
  }
  return pages
})

const goToPage = (page) => {
  if (page < 1 || page > totalPages.value || page === '...') return
  currentPage.value = page
  // Scroll suave al inicio de la sección de artículos
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<template>
  <div class="py-12 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">

    <!-- Hero Section -->
    <header class="mb-16 md:mb-20">
      <span class="text-xs font-bold text-secondary uppercase tracking-[0.2em] mb-4 block">Bitácora de Viaje</span>
      <h1 class="font-display text-4xl md:text-5xl text-primary mb-6 font-bold leading-tight max-w-3xl">
        Historias talladas en piedra, barro y naturaleza.
      </h1>
      <p class="font-body text-base md:text-lg text-on-surface-variant max-w-2xl leading-relaxed">
        Rivera es más que un destino; es una narrativa viva. Explora las crónicas de nuestra tierra, desde el legado literario de La Vorágine hasta los secretos de nuestros maestros artesanos.
      </p>
    </header>

    <!-- Contador de artículos -->
    <div class="flex items-center justify-between mb-8">
      <p class="text-on-surface-variant text-xs font-semibold uppercase tracking-wider">
        Mostrando {{ (currentPage - 1) * ARTICLES_PER_PAGE + 1 }}–{{ Math.min(currentPage * ARTICLES_PER_PAGE, allArticles.length) }}
        de {{ allArticles.length }} artículos
      </p>
    </div>

    <!-- Articles Grid -->
    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-16">
      <article
        v-for="(article, index) in paginatedArticles"
        :key="article.id"
        class="group cursor-pointer flex flex-col"
        :class="index === 0 && currentPage === 1 ? 'md:col-span-2' : ''"
      >
        <div
          class="relative overflow-hidden rounded-2xl border border-secondary/15 bg-surface shadow-sm transition-all duration-300 hover:-translate-y-2 hover:shadow-xl flex flex-col flex-grow"
        >
          <!-- Image -->
          <div
            class="overflow-hidden"
            :class="index === 0 && currentPage === 1 ? 'aspect-[21/9] md:aspect-[3/1]' : 'aspect-[16/9]'"
          >
            <img
              :alt="article.title"
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
              :src="article.img"
            />
          </div>

          <!-- Content -->
          <div class="p-6 md:p-8 flex flex-col flex-grow justify-between">
            <div>
              <div class="flex items-center gap-3 mb-4 text-[11px] font-bold">
                <span :class="['px-3 py-1 rounded-full uppercase tracking-wider', article.categoryColor]">
                  {{ article.category }}
                </span>
                <span class="text-on-surface-variant uppercase tracking-wider flex items-center gap-1">
                  <span class="material-symbols-outlined text-[14px]">schedule</span>
                  {{ article.readTime }} DE LECTURA
                </span>
              </div>
              <h2
                class="font-display font-bold text-primary mb-3 group-hover:text-secondary transition-colors leading-tight"
                :class="index === 0 && currentPage === 1 ? 'text-2xl md:text-3xl' : 'text-xl'"
              >
                {{ article.title }}
              </h2>
              <p class="text-on-surface-variant text-sm mb-6 leading-relaxed line-clamp-3">
                {{ article.excerpt }}
              </p>
            </div>
            <div class="flex items-center text-secondary font-bold text-xs gap-2 group-hover:translate-x-1 transition-transform">
              {{ article.cta }}
              <span class="material-symbols-outlined text-sm">arrow_forward</span>
            </div>
          </div>
        </div>
      </article>
    </div>

    <!-- ── Paginador ─────────────────────────────────────────────────────── -->
    <nav
      v-if="totalPages > 1"
      class="flex items-center justify-center gap-2 mb-24"
      aria-label="Paginación del blog"
    >
      <!-- Anterior -->
      <button
        @click="goToPage(currentPage - 1)"
        :disabled="currentPage === 1"
        class="flex items-center gap-1 px-4 py-2 rounded-full text-xs font-bold border transition-all"
        :class="currentPage === 1
          ? 'border-outline-variant text-outline cursor-not-allowed opacity-40'
          : 'border-primary text-primary hover:bg-primary hover:text-on-primary'"
        aria-label="Página anterior"
      >
        <span class="material-symbols-outlined text-sm">chevron_left</span>
        Anterior
      </button>

      <!-- Números de página -->
      <template v-for="page in visiblePages" :key="page">
        <!-- Elipsis -->
        <span
          v-if="page === '...'"
          class="px-3 py-2 text-xs text-on-surface-variant select-none"
        >
          …
        </span>
        <!-- Número de página -->
        <button
          v-else
          @click="goToPage(page)"
          class="w-9 h-9 rounded-full text-xs font-bold border transition-all"
          :class="page === currentPage
            ? 'bg-primary text-on-primary border-primary shadow-md scale-110'
            : 'border-outline-variant text-on-surface-variant hover:border-primary hover:text-primary'"
          :aria-label="`Ir a página ${page}`"
          :aria-current="page === currentPage ? 'page' : undefined"
        >
          {{ page }}
        </button>
      </template>

      <!-- Siguiente -->
      <button
        @click="goToPage(currentPage + 1)"
        :disabled="currentPage === totalPages"
        class="flex items-center gap-1 px-4 py-2 rounded-full text-xs font-bold border transition-all"
        :class="currentPage === totalPages
          ? 'border-outline-variant text-outline cursor-not-allowed opacity-40'
          : 'border-primary text-primary hover:bg-primary hover:text-on-primary'"
        aria-label="Página siguiente"
      >
        Siguiente
        <span class="material-symbols-outlined text-sm">chevron_right</span>
      </button>
    </nav>

    <!-- Newsletter Section -->
    <section class="p-8 md:p-16 bg-surface-container rounded-3xl border border-secondary/15 text-center max-w-4xl mx-auto">
      <h2 class="font-display text-2xl md:text-3xl text-primary mb-4 font-bold">¿Desea recibir nuestras crónicas?</h2>
      <p class="text-on-surface-variant text-sm mb-10 max-w-lg mx-auto leading-relaxed">
        Suscríbase a nuestro boletín mensual para recibir historias exclusivas y novedades de Rivera directamente en su correo.
      </p>
      <form class="flex flex-col md:flex-row gap-4 max-w-md mx-auto" @submit.prevent>
        <input
          required
          class="flex-grow px-6 py-3 rounded-full border border-outline-variant focus:border-secondary focus:ring-2 focus:ring-secondary/40 bg-surface-container-lowest outline-none text-sm text-on-surface"
          placeholder="Su correo electrónico"
          type="email"
        />
        <button
          class="bg-secondary text-on-secondary px-8 py-3 rounded-full font-bold text-sm hover:scale-105 transition-transform duration-200"
          type="submit"
        >
          Suscribirse
        </button>
      </form>
    </section>

  </div>
</template>
