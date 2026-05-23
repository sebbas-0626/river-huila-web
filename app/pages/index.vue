<script setup>
const isBookingOpen = useState('isBookingOpen', () => false)

const openBooking = () => {
  isBookingOpen.value = true
}

useSeoMeta({
  title: 'Rivera Turística - Donde el Pasado se Pinta de Verde',
  description: 'Descubre el equilibrio perfecto entre la arquitectura colonial, el bienestar termal y la exuberante naturaleza de Rivera, Huila.'
})
</script>

<template>
  <div>
    <!-- Hero Section -->
    <section class="relative h-[85vh] min-h-[600px] flex items-center overflow-hidden">
      <div class="absolute inset-0 z-0">
        <img 
          alt="Paisaje de Rivera" 
          class="w-full h-full object-cover" 
          src="https://lh3.googleusercontent.com/aida-public/AB6AXuAANq_rfScHPnakNB3ZZSZln0fluByHMobhnCgtu-ODFFGB0Q_tKb7EOYdJYSrHz98Z0400Myn_FB6zq2ba-YO34kCcUSnonu2F_e7ZV5rW69KJiHLJCrwIgYfy-Utl-vVgm9XDp9KJDHvT_airWAKUPgfZGtbhYLaeC1cjjVFtCdGcndSULh0crCX8mf4EXJkhgCtirYMlJptNt0PGE7xf-yJe9AHPUYZR4Et-SQrbrVaKsj8qIZH8iUkn_PFdKVEzCw9pnG10UQE"
        />
        <div class="absolute inset-0 bg-gradient-to-r from-primary/70 via-primary/30 to-transparent"></div>
      </div>
      <div class="relative z-10 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto w-full">
        <div class="max-w-2xl text-white">
          <h1 class="font-display text-4xl md:text-6xl mb-6 leading-tight font-bold drop-shadow-md">
            Rivera Donde el Pasado se Pinta de Verde e Historia
          </h1>
          <p class="font-sans text-lg md:text-xl mb-8 opacity-90 max-w-lg">
            Descubre el equilibrio perfecto entre la arquitectura colonial, el bienestar termal y la exuberante naturaleza del Huila.
          </p>
          <div class="flex flex-col sm:flex-row gap-4">
            <NuxtLink 
              to="/planifica" 
              class="bg-primary text-on-primary px-8 py-4 rounded-lg font-semibold text-center flex items-center justify-center gap-2 transition-transform hover:-translate-y-1 shadow-lg"
            >
              Planea tu viaje
              <span class="material-symbols-outlined text-sm">arrow_forward</span>
            </NuxtLink>
            <button 
              @click="openBooking"
              class="bg-white/15 backdrop-blur-md text-white border border-white/30 px-8 py-4 rounded-lg font-semibold hover:bg-white/25 transition-all"
            >
              Reservar Experiencia
            </button>
          </div>
        </div>
      </div>
    </section>

    <!-- Plan Fachada Section (Interactive) -->
    <section class="py-24 bg-surface">
      <div class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div class="relative">
            <div class="rounded-xl overflow-hidden shadow-2xl relative">
              <img 
                alt="Plan Fachada Rivera" 
                class="w-full h-[500px] object-cover" 
                src="https://lh3.googleusercontent.com/aida-public/AB6AXuBw-0boUM_m0kCrBNeoMYfJqFeK1A4eBc2w25ogEwJ_iiNw6Cbv2pxri-Iy7ZEihQlSfEiuqxRI-_KlnfxqjOACV-wf1PZ_5GhlWd5OjAvTtlDSdsr3cc-KrqPrMmbWO3jt_dNz63EckapqJHIbLbSYTDQZMUJ3-hHyYI92VOQdfT_gJVCYpIL8EdIQrYB3SyK3kuZqnzEl9JWEFHDVCXV0ZTEcTpGkY0rkw5YR6Lodu62xVn2RzFf6gTQ36kuFLMPMce2qUDG25TI"
              />
              <div class="absolute bottom-6 right-6 glass-morphism p-6 rounded-lg shadow-xl max-w-xs border border-white/40">
                <h4 class="font-display text-lg text-primary mb-2 font-bold">Identidad Viva</h4>
                <p class="text-on-surface-variant text-xs font-medium">Cada trazo de color en nuestras fachadas coloniales rescata nuestra memoria histórica.</p>
              </div>
            </div>
          </div>
          <div>
            <span class="text-xs font-bold text-secondary uppercase tracking-widest mb-4 block">Legado y Belleza</span>
            <h2 class="font-display text-3xl md:text-4xl text-on-surface mb-6 font-bold leading-tight">El Plan Fachada: Un Renacer Colonial</h2>
            <p class="font-body text-base text-on-surface-variant mb-8 leading-relaxed">
              Nuestra iniciativa de embellecimiento transforma las calles de Rivera en un lienzo vivo. Inspirados en los colores tradicionales de la tierra y el bosque, devolvemos el esplendor a nuestras raíces coloniales.
            </p>
            <div class="space-y-6">
              <div class="flex gap-4 items-start">
                <div class="bg-primary-container p-3 rounded-full text-on-primary-container flex items-center justify-center">
                  <span class="material-symbols-outlined">brush</span>
                </div>
                <div>
                  <h4 class="font-semibold text-sm text-on-surface mb-1">Colores Tradicionales</h4>
                  <p class="text-on-surface-variant text-sm">Uso de pigmentos minerales que evocan la cal, el verde bosque y la arcilla de antaño.</p>
                </div>
              </div>
              <div class="flex gap-4 items-start">
                <div class="bg-secondary-container p-3 rounded-full text-on-secondary-container flex items-center justify-center">
                  <span class="material-symbols-outlined">history_edu</span>
                </div>
                <div>
                  <h4 class="font-semibold text-sm text-on-surface mb-1">Restauración Consciente</h4>
                  <p class="text-on-surface-variant text-sm">Preservación de molduras y carpintería original de madera en el centro histórico.</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Bento Grid - Experiencias -->
    <section class="py-24 bg-surface-container-low overflow-hidden">
      <div class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
        <div class="text-center mb-16">
          <h2 class="font-display text-3xl md:text-4xl text-on-surface font-bold">Experiencias Rivera</h2>
          <p class="font-body text-sm text-on-surface-variant mt-4">Descubre lo que hace única a nuestra tierra.</p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-12 gap-gutter">
          <!-- Bienestar (Termales) -->
          <div class="md:col-span-8 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl h-[400px] md:h-[450px]">
            <img 
              alt="Termales Rivera" 
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuBDqv7oVJBqNRDpGYhvWr4P1qhSosq0ufo3i9kyJOZ61WGkJZ1ICjyz5eTalASlkI-bw87zM_lAZBrHtenAbP5UWkbFbKpS7wxE6zEW9cHT4SQ0jAVTodgXgnKEZ2i648fNIfLAqKauwj0_eqZuU_h-FavC6cjkOD3zJ3scG3YIVbSlJXRfqejuO_QxVRXor0MhYkNqh_lAwlLQUda1WaRfoZqAJ-RJcNJ-Tv8Ose-eo39UN7xWKMlCOCr81_U1CozdiTnfII35fMY"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/35 to-transparent flex flex-col justify-end p-8 md:p-10">
              <span class="bg-tertiary-fixed text-on-tertiary-fixed px-3 py-1 rounded-full text-xs font-bold w-fit mb-4">Bienestar</span>
              <h3 class="font-display text-2xl md:text-3xl text-white mb-2 font-bold">Termales de Rivera</h3>
              <p class="text-white/80 max-w-md text-sm">Relájate en aguas medicinales rodeado de la paz y el verdor del bosque tropical.</p>
            </div>
          </div>

          <!-- Ecoturismo (Cascadas) -->
          <div class="md:col-span-4 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl h-[400px] md:h-[450px]">
            <img 
              alt="Cascadas en Rivera" 
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuDdYBvG6f6NonMXX8F8uD1ohDDffEn2AGtMVs1eU_a8yaFkmAx2JgI2KkffbyuuQw9oWr5jSaYZDrmQEbt1IxurGuVSLPMVRyOgDDFR4Ou_VJf5VyVrHiMJ36iMHHofsPlZPGAFGwosCMe-0aU8lxENpjE-nleaQiMEYwNAeDbMW9BFkZQElOxprOm8pfuFdD4yfGSUDdMWnvLk-pAl_f5MIXvgUVKGrWEnS3DCeyPk31l57NnhqZNfQAPPiyC5Z7RM5oRxRFdZvUE"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/35 to-transparent flex flex-col justify-end p-8">
              <span class="bg-primary-fixed text-on-primary-fixed px-3 py-1 rounded-full text-xs font-bold w-fit mb-3">Ecoturismo</span>
              <h3 class="font-display text-xl md:text-2xl text-white mb-2 font-bold">Cascadas y Senderos</h3>
              <p class="text-white/80 text-sm">Aventura y conexión espiritual en el corazón de la naturaleza huilense.</p>
            </div>
          </div>

          <!-- Cultura (Achiras y Vinos) -->
          <div class="md:col-span-4 group relative overflow-hidden rounded-xl shadow-lg transition-all duration-500 hover:shadow-2xl h-[300px] md:h-[350px]">
            <img 
              alt="Sabor Rivera" 
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuBZgW2x8G6MiihV-7_Cr-OCwRKE5AOgLqJrnXAVo1_u9nc75Zfs4Kmd3JhdFJD0PwKJuupBUws_LiW6SU6y9A8D_UY1373hKPaBY75eq7fi6O38IPRC4Pe3QFkEDCxlbjB-3m0TVJ-BYA1_LrvFrtDZFIhYEpXpbDRtEkqLhFsPm_DBUbY46P9OjdiPX8qJ2ZK9q3hRg0hOc3GzQnFmoPwa-A5nnttr0f5dG3Cs-rWdt3OkW1sgcwcXY76hKKL96c_scvCs19J4pWE"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/35 to-transparent flex flex-col justify-end p-8">
              <span class="bg-secondary-fixed text-on-secondary-fixed px-3 py-1 rounded-full text-xs font-bold w-fit mb-3">Cultura</span>
              <h3 class="font-display text-xl md:text-2xl text-white mb-2 font-bold">Sabor y Gastronomía</h3>
              <p class="text-white/80 text-sm">Deleita tu paladar con achiras calientes y vinos de frutas artesanales.</p>
            </div>
          </div>

          <!-- CTA Block -->
          <div class="md:col-span-8 bg-primary-container rounded-xl flex flex-col items-center justify-center p-8 md:p-12 text-center relative overflow-hidden shadow-lg h-[300px] md:h-[350px]">
            <div class="absolute inset-0 opacity-10 pointer-events-none" style="background-image: radial-gradient(#ffffff 1px, transparent 1px); background-size: 20px 20px;"></div>
            <div class="relative z-10 max-w-md">
              <h3 class="font-display text-2xl md:text-3xl text-on-primary-container mb-6 font-bold leading-tight">
                ¿Listo para programar tu viaje a Rivera?
              </h3>
              <div class="flex flex-col sm:flex-row justify-center gap-4">
                <NuxtLink 
                  to="/directorio" 
                  class="bg-white text-primary font-bold text-sm px-8 py-3 rounded-full hover:shadow-xl hover:scale-105 transition-all text-center"
                >
                  Explorar Directorio
                </NuxtLink>
                <button 
                  @click="openBooking" 
                  class="bg-secondary text-on-secondary font-bold text-sm px-8 py-3 rounded-full hover:shadow-xl hover:scale-105 transition-all"
                >
                  Reservar Ahora
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Newsletter -->
    <section class="py-24 bg-surface">
      <div class="px-margin-mobile md:px-margin-desktop max-w-[800px] mx-auto text-center">
        <h2 class="font-display text-3xl md:text-4xl text-on-surface mb-6 font-bold">Suscríbete a nuestra guía de viaje</h2>
        <p class="text-on-surface-variant mb-10 text-base md:text-lg">
          Recibe recomendaciones exclusivas de gastronomía, eventos de tradición y ofertas de hospedajes termales en tu email.
        </p>
        <form @submit.prevent="alert('¡Gracias por suscribirte!')" class="flex flex-col sm:flex-row gap-4">
          <div class="flex-grow clay-border rounded-lg bg-white overflow-hidden flex items-center px-4">
            <span class="material-symbols-outlined text-outline">mail</span>
            <input 
              required
              class="w-full border-none focus:ring-0 py-4 px-3 bg-transparent text-sm text-on-surface" 
              placeholder="Tu correo electrónico" 
              type="email"
            />
          </div>
          <button 
            type="submit"
            class="bg-secondary text-on-secondary px-8 py-4 rounded-lg font-bold text-sm hover:bg-secondary-container transition-colors shadow-md"
          >
            Unirme
          </button>
        </form>
      </div>
    </section>
  </div>
</template>
