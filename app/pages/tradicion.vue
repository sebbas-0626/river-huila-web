<script setup>
useSeoMeta({
  title: 'Tradición y Cultura - Rivera Huila',
  description: 'Explora la rica historia y patrimonio de Rivera, el municipio verde de Colombia.'
})

const moments = [
  {
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAOGH9DRJfXreO2Nttn0lEeWAmQ-OzqE23vOGqxHSjmgAMlbLgFtE-BFY9Cf95ndvx7nNh376_9QFM56TYiB3TyR6vEHVl1VYOGkQQkELyJ9AXiaoiwmEmmVtDR2NCJtBnQTuoBx7r4HVktcohRj-PBbJkQ9RARxFnbMZqD2QM0T4Tyxyx6zlNzC0uW_37-ReZ6N5HS9DBscI6QzARI6E_8wTkf7gJHZBRqwwcp-HDOx6cCks15GVxssHGYHIXbB1jCLcjnCzZFIYo',
    alt: 'Disfrutando bizcochos de achira en Rivera'
  },
  {
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDUY2zfYNglZn5oVPxwLHA85mfFbX7tVMn2ZRj-JPTgje2JPSRzZGy79cXbhOxQfev9L53eWx0sudgqROeJSPElxueJ30gY8313iJQUKFV5MtDnwM0Q8ATynv01u_Mbc_iNO9jscwHdHbZ7QpfqFA9WGe3cEoX2_pGMhaP1-ml0JQTzTPrIZ-yidWrxovLypmCpvmcG-iUvDKdMyEZiwCpa0RJVC1qUNnU2nijDyu8KZyvoW_Lwag3nMBzcfMsZv4cp1qwIkImkemw',
    alt: 'Senderismo en bosque tropical de Rivera'
  },
  {
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAmYMbIN0ZhyMdfExw2cfaLSVMiBDkcpoOU7Y0CdkuAEiOxoA5t6AX-BLW5MYca81MSx7B2Pr3yn60SUihnNzf_90Q2UE9BCG-fx3v396wmxscjbo08NtP85zb1Qij-7p5zy0bPXHF0Sjkm6HuqOjnNQQu2-l2slB3KQLzr0fg6LxN0r3uby2ILLQk-ksMarqy3S9auVzGcPdRwJK4cGShQstVK9CspQSSLPVkD3j2Xv2zIPDYn2IHPX46UJiY8HjuctrwBJenZRr0',
    alt: 'Café artesanal en la montaña de Rivera'
  },
  {
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuAh_NejcUyX61WV70AtQ_256sGPpnz3LZIPfb8QJ07828njD4-xMG2vBzSJBOIBrPLeWV3_uodnqDuaJIqP1blK3egzv6kE9E0ofSaLTMDL25xn3Lgtsf_aZHplqwVJFAN02mhYS-yTEOynL36FTfqRB7iE6BuG-g4ObnzmTav5dBultY6zqkeyx7epnTc3Kd_MCZsJr4pMSg1z-dkhAhI0xsn8w3uMRgoy2dlJCT4CltyssWGLZew0gqUfzOeC8E4EM4wxyNSZ7Fo',
    alt: 'Atardecer en Rivera Huila'
  },
  {
    img: 'https://lh3.googleusercontent.com/aida-public/AB6AXuDwFtQx_H0ejq7VMGhojFLlk9M_B_nnMhADxJ_gL_oKY1WZSPnLZtkST2YU1AV9HKY3SWLMdyskQnvAi8vzsteNQAH-2I_-yzBuWKZsHFjq0USxGqtohYeMCYL9xdrNYNKYAMV--ARXxEl8on3Rt74NpAx3pMiAQxur-7aDuoyQpoaUJD6M6tXwUV2_W-lKUgf5dehrl2nZCUhCIRCwOqHF4d03-Z5xhqr-AkZxeDXhZ9kanlRtGzPl_UQvHcb7MSHm8ZqTHZsB7BU',
    alt: 'Calle colonial decorada de Rivera'
  }
]
</script>

<template>
  <div>
    <!-- Split Image Hero Section -->
    <section class="relative h-[85vh] min-h-[600px] flex items-center overflow-hidden">
      <div class="absolute inset-0 z-0 flex">
        <!-- Split imagery: Colonial vs Nature -->
        <div class="w-1/2 h-full relative overflow-hidden group">
          <img 
            class="w-full h-full object-cover transition-transform duration-1000 group-hover:scale-105" 
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuDtG9LF4reeBbtw45DMmsud2GJ3QuAR7_lr81tlTGJCEiIcC_jm4Vfv6WnhtrJfUtMMcAe9TIhLewDVDtMadH4Mkw18UUqx5XhEXx7RPozsOd9Konrk_T0ZQp_GgoX6RONcHdtzRpBZXgQD1PaBTNpjIufDck3nttuSr4AOzN_MyfzbHJ7Lk4hi_LLxJVmWHw2pEBaCo-gpW9enZua6ADZnUDrkd1ZewFHAvhmwxMHOkgTT0jsqKc1LHP6kP7LEjJO6tQSMpoladXo"
            alt="Arquitectura Colonial"
          />
          <div class="absolute inset-0 bg-primary/20 mix-blend-multiply"></div>
        </div>
        <div class="w-1/2 h-full relative overflow-hidden group">
          <img 
            class="w-full h-full object-cover transition-transform duration-1000 group-hover:scale-105" 
            src="https://lh3.googleusercontent.com/aida-public/AB6AXuCzA4Cb3fSMgNiWUjppeyLSPF-N1tWw7-u6oAHFcFkIXIeeDgC2rsuOi2AxpL-TrRXCwifOR2gYtUv6CExYxdr7l-Bz43z6L_MDNIHtlfxW1QqHiTX_9kcgjwSBHJjHsXyxdqGdNdqF4nfKrSeizknwJveFQcbcG5KUZoZp9vKGMM3tdyi_gi2lVXvd8Qo1LdtLAQT9PuLslBdyAxGJcLfd5fmDj3Lv4u1XtxFFAEVw9jjeHP2tFg8GpitZugrRBXzrsBmKRQfCPbw"
            alt="Naturaleza y Montañas"
          />
          <div class="absolute inset-0 bg-tertiary/20 mix-blend-multiply"></div>
        </div>
      </div>
      <div class="relative z-10 w-full px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto text-center md:text-left">
        <div class="max-w-2xl bg-surface/35 backdrop-blur-md p-8 md:p-12 rounded-2xl border border-white/20">
          <h1 class="font-display text-4xl md:text-6xl text-white mb-6 font-bold leading-tight drop-shadow-md">
            Rivera, Huila: Tradición que Florece
          </h1>
          <p class="font-sans text-lg text-white/90 mb-10 max-w-xl">
            Descubre el pueblo verde del Huila, donde la historia colonial cobra vida entre termales y montañas.
          </p>
          <div class="flex flex-col sm:flex-row gap-4">
            <NuxtLink 
              to="/lugares" 
              class="bg-primary text-on-primary px-8 py-4 rounded-xl font-semibold text-center flex items-center justify-center gap-2 hover:translate-y-[-2px] transition-all shadow-md"
            >
              Explorar Rutas 
              <span class="material-symbols-outlined text-sm">arrow_forward</span>
            </NuxtLink>
            <NuxtLink 
              to="/agenda" 
              class="bg-white/10 hover:bg-white/20 backdrop-blur-sm text-white border border-white/30 px-8 py-4 rounded-xl font-semibold text-center transition-all"
            >
              Agenda de Eventos
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>

    <!-- El Renacer de Rivera (Plan Fachada) -->
    <section class="py-24 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto overflow-hidden">
      <div class="grid grid-cols-1 md:grid-cols-12 gap-gutter items-center">
        <div class="md:col-span-5 space-y-6">
          <span class="text-secondary font-bold text-xs uppercase tracking-[0.2em]">Arquitectura Viva</span>
          <h2 class="font-display text-3xl md:text-5xl text-primary font-bold leading-tight">El Renacer de Rivera</h2>
          <p class="font-body text-base text-on-surface-variant leading-relaxed">
            Nuestro "Plan Fachada" rescata el alma de Rivera. Hemos restaurado las líneas coloniales tradicionales para que cada calle cuente una historia de orgullo huilense y hospitalidad.
          </p>
          <blockquote class="border-l-4 border-secondary pl-6 py-2 italic font-display text-xl text-secondary">
            "Caminamos hacia el futuro honrando nuestro pasado."
          </blockquote>
          <div class="pt-4">
            <NuxtLink to="/blog" class="text-primary font-bold text-sm flex items-center gap-2 group">
              Conoce el proyecto 
              <span class="material-symbols-outlined group-hover:translate-x-1 transition-transform">trending_flat</span>
            </NuxtLink>
          </div>
        </div>

        <div class="md:col-span-7 relative">
          <div class="grid grid-cols-2 gap-4">
            <div class="space-y-4 pt-12">
              <div class="rounded-2xl overflow-hidden shadow-2xl rotate-[-2deg]">
                <img 
                  class="w-full aspect-[3/4] object-cover" 
                  src="https://lh3.googleusercontent.com/aida-public/AB6AXuC-mG1yJ-3ejaWpgNP9XMWa-4j6tYouy_hI2gu6CCJNXdNch33cGPdWDfIzXk-1m8wt8FFmf_HHTN5vY18PQfG-cnkOSiYvWhGha2U8xM1jiu_pUVYfFs3BXchiPLZeuOukGSlEJ8rvyqqqdJBopgJDoBSXjmdluR345VF8Zfx8foaIgbH3sxLqSxdoygw6olxAdm8oBxUmnSQrYgfa5DRPXNnTx8tFSFyX-ksL5pLgqcUb23fAyG9z20hKaAAOTWoCgIo9nlExUWU"
                  alt="Restauración de Madera"
                />
              </div>
            </div>
            <div class="space-y-4">
              <div class="rounded-2xl overflow-hidden shadow-2xl rotate-[2deg]">
                <img 
                  class="w-full aspect-square object-cover" 
                  src="https://lh3.googleusercontent.com/aida-public/AB6AXu-SuiOth8H04UDFb-lco1aMi-itOafSBq2-Wee-J9mcsCz7fD6LkbkKILcDsx2WXUFScESknz9hL9bSHvTVIHfE5YMG1i9VVqq2pTr1Uyb8Rq008BhOjU90izl4y2NLGL-_HimypmP51UD08Qc_XN6apxhSonmfrxpaBtdYKg6pxe4OqYZXBkvGvx8Xf2h42aedAHtNQb1hqOrNtql3fcqVBm3EdJAwaetXxCrowNSrjR8KS_xO_6ftjdMhBNTQHrcgeEcJ2909EE"
                  alt="Vista del Pueblo"
                />
              </div>
              <div class="bg-tertiary-fixed rounded-2xl p-8 flex flex-col justify-end min-h-[180px] shadow-md">
                <h3 class="text-on-tertiary-fixed font-display text-4xl font-bold">85%</h3>
                <p class="text-on-tertiary-fixed-variant text-xs font-bold uppercase tracking-wider">Fachadas Restauradas</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Galería Social / Momentos -->
    <section class="py-24 bg-surface-container-low overflow-hidden">
      <div class="px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto mb-12 flex justify-between items-end">
        <div>
          <span class="text-xs font-bold text-secondary uppercase tracking-widest mb-2 block">Experiencia Real</span>
          <h2 class="font-display text-3xl md:text-4xl text-primary font-bold">Momentos Rivera</h2>
          <p class="text-on-surface-variant text-sm mt-2">Etiquétanos y sé parte de nuestra historia: <span class="text-secondary font-bold">#RiveraHuila</span></p>
        </div>
        <a 
          href="https://instagram.com" 
          target="_blank" 
          class="hidden md:flex items-center gap-2 bg-surface text-primary border border-primary px-6 py-2.5 rounded-full font-bold text-sm hover:bg-primary hover:text-on-primary transition-all shadow-sm"
        >
          Ver Instagram 
          <span class="material-symbols-outlined text-[18px]">photo_camera</span>
        </a>
      </div>

      <!-- Horizontal Scrollable Container -->
      <div class="flex gap-6 overflow-x-auto pb-8 snap-x no-scrollbar px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
        <div 
          v-for="(moment, idx) in moments" 
          :key="idx" 
          class="snap-center flex-shrink-0 w-72 aspect-square rounded-2xl overflow-hidden shadow-lg hover:scale-102 transition-all duration-300"
        >
          <img 
            class="w-full h-full object-cover" 
            :src="moment.img" 
            :alt="moment.alt"
          />
        </div>
      </div>
    </section>
  </div>
</template>
