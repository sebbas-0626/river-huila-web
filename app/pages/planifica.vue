<script setup>
import { ref } from 'vue'

useSeoMeta({
  title: 'Planifica tu Viaje - Rivera Huila',
  description: 'Prepara tu viaje a Rivera. Rutas turísticas recomendadas, mapa interactivo, consejos de clima, vestuario y transporte.'
})

const selectedLocation = ref('termales')

const locations = {
  termales: {
    title: 'Termales Los Ángeles',
    sub: 'A 15 min del centro',
    desc: 'Aguas termales 100% naturales, perfectas para relajación nocturna en un entorno campestre rodeado de bosque.',
    coords: 'top-1/3 left-[45%]'
  },
  parque: {
    title: 'Parque Principal',
    sub: 'Centro histórico',
    desc: 'El corazón colonial de Rivera, ideal para degustar bizcochos de achira calientes y helado de cholupa bajo las ceibas.',
    coords: 'top-1/2 left-[25%]'
  },
  mirador: {
    title: 'Mirador del Quinde',
    sub: 'Ruta Aventura',
    desc: 'Punto de partida para senderismo y avistamiento de aves con espectaculares panorámicas del cañón del río Rivera.',
    coords: 'top-1/4 right-[30%]'
  }
}
</script>

<template>
  <div>
    <!-- Hero Section -->
    <section class="relative h-[55vh] flex items-center justify-center overflow-hidden">
      <img 
        alt="Paisaje de Rivera" 
        class="absolute inset-0 w-full h-full object-cover" 
        src="https://lh3.googleusercontent.com/aida-public/AB6AXuD_u-RE5Ss40kYAweWeHm2hbeVAbcRPI_JTOCP632OJ6j95bBmNfuFCfbJRFWa7eUcRqLpG2mXdYYqAavLPw44P9kLjQFDrUzPrKXy-F_HfKiaWBtHl7CGdjlWQeLZQjtvKNfpklMJopsLR8QhafpOPCGxRg6RcBYfAfI09KvACzEUoqfz6Z5oPHZEuOQgKU38CxVsRv62smlQHMQZYfjV2rHh_Tspp6gYLZqh2jCBsOjbyJrVfNEYBZgsXfAHZ_LCPRiKukc-SK0w"
      />
      <div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/30 to-transparent"></div>
      <div class="relative z-10 text-center px-margin-mobile max-w-3xl mx-auto">
        <h1 class="font-display text-4xl md:text-5xl text-white mb-4 font-bold">Planifica tu Viaje</h1>
        <p class="font-body text-base md:text-lg text-white/90 leading-relaxed">
          Descubre la armonía entre la naturaleza exuberante y el legado colonial en el corazón del departamento del Huila.
        </p>
      </div>
    </section>

    <!-- Suggested Routes Section -->
    <section class="py-20 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-end mb-12 gap-6">
        <div>
          <span class="text-xs font-bold text-secondary uppercase tracking-widest mb-2 block">Explora a tu Ritmo</span>
          <h2 class="font-display text-3xl md:text-4xl text-primary font-bold">Rutas Sugeridas</h2>
        </div>
        <a 
          href="/docs/guia_rivera.pdf" 
          download 
          class="flex items-center gap-2 text-primary font-bold text-xs border-b border-primary pb-1 hover:pb-2 transition-all"
        >
          <span class="material-symbols-outlined text-sm">download</span>
          Descargar Guía Digital (PDF)
        </a>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-gutter">
        
        <!-- Ruta Relax -->
        <div class="group bg-white rounded-xl overflow-hidden shadow-md border border-outline-variant hover:shadow-xl transition-all duration-300">
          <div class="h-56 overflow-hidden relative">
            <img 
              alt="Aguas Termales" 
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105" 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuAIPEHGmH1R_tPPP1UolYHqyLbzwlhRl9UQxRmDiLYLojew9t8qYpvbC7DIBMUb7NjMn7NUydb7a0BcU5YsktuaCX5khfOR1pMOvqvqHiKYumdTdldzikOoXoN_Iy5jKHHitXNoaftFf06ZigoYuB1Q6W7IreuMe-I11U89VF_ibdl-59igQip61FD5WOphF40uBpWPG0drbl2hS7Z20VIp0Iu9mgJVxrsmCsUMffrMUFjkbIzf2ycJ2fmfvUaHVt_sj0vO-ULU6Iw"
            />
            <div class="absolute top-4 left-4 bg-tertiary text-on-tertiary px-3 py-1 rounded-full text-[10px] font-bold tracking-wider">1 DÍA</div>
          </div>
          <div class="p-8">
            <h3 class="font-display text-xl text-primary mb-4 font-bold">Ruta Relax</h3>
            <ul class="space-y-4 mb-8 text-sm text-on-surface-variant font-medium">
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">spa</span>
                <span>Baños termales medicinales para renovar cuerpo y mente.</span>
              </li>
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">restaurant</span>
                <span>Almuerzo típico tradicional (Asado Huilense).</span>
              </li>
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">icecream</span>
                <span>Degustación de postres y achiras calientes.</span>
              </li>
            </ul>
            <button class="w-full py-3 border border-outline-variant rounded-lg font-bold text-xs text-primary hover:bg-surface-container-low transition-colors">
              Ver Detalles
            </button>
          </div>
        </div>

        <!-- Ruta Aventura -->
        <div class="group bg-white rounded-xl overflow-hidden shadow-md border border-outline-variant hover:shadow-xl transition-all duration-300">
          <div class="h-56 overflow-hidden relative">
            <img 
              alt="Cascada Salto del Ángel" 
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105" 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuCj_qEYhFrI3CJ7HOTKOAoiPOgHlTR1pwI1-euet2gyPtyFRfp1IVjFKmziGEAhCR-shcYKb1lCIfvttdakx7tgP9FPAX2lmyY40KAki3QdrYIJPZg5HcdHwzcwVXM-R-Hcr6ezAj2g9RvbeNtzLFRAlDQAw4lx9EFVrXbHFp03YRg6j1k19FiTh4A6TKVIaJxe8jbNQsmTxgSii0uBUS0ftoqFz-YPIRba3N4el2IOk-pgq8jlhtME7kFejSrSwW5DwAmuE2AihY0"
            />
            <div class="absolute top-4 left-4 bg-tertiary text-on-tertiary px-3 py-1 rounded-full text-[10px] font-bold tracking-wider">2 DÍAS</div>
          </div>
          <div class="p-8">
            <h3 class="font-display text-xl text-primary mb-4 font-bold">Ruta Aventura</h3>
            <ul class="space-y-4 mb-8 text-sm text-on-surface-variant font-medium">
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">waterfall_chart</span>
                <span>Trekking al Salto del Ángel y cascadas de montaña.</span>
              </li>
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">camping</span>
                <span>Noche en domo de glamping bajo las estrellas del Huila.</span>
              </li>
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">hiking</span>
                <span>Senderismo guiado por el cañón de Los Arrayanes.</span>
              </li>
            </ul>
            <button class="w-full py-3 border border-outline-variant rounded-lg font-bold text-xs text-primary hover:bg-surface-container-low transition-colors">
              Ver Detalles
            </button>
          </div>
        </div>

        <!-- Ruta Identidad -->
        <div class="group bg-white rounded-xl overflow-hidden shadow-md border border-outline-variant hover:shadow-xl transition-all duration-300">
          <div class="h-56 overflow-hidden relative">
            <img 
              alt="Calle colonial Rivera" 
              class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105" 
              src="https://lh3.googleusercontent.com/aida-public/AB6AXuB4F6mkApuzQsDBFUCgXAj612IVW5ja0zE60Jv2f3vO60140PCSXOcxHtuMWxymtbgoPmAmdnifcgQ09CzPl7bPOk1gXATHfYN1T-27POzZ1Yfv5csFkrVOWCbqqfABQqb7btvKOrZd8JFj203YJ9F212CeIKZGQoNMrt5vwZU6Hz-spXsVqMQBSKXkXChDDhd2VMAmAnQDHVGzgN7fBHEQnD0tJt3D45alOgKbrtcISpQrwN4EKAHCTRquPHgasFp-7peit7lfKmE"
            />
            <div class="absolute top-4 left-4 bg-tertiary text-on-tertiary px-3 py-1 rounded-full text-[10px] font-bold tracking-wider">MEDIO DÍA</div>
          </div>
          <div class="p-8">
            <h3 class="font-display text-xl text-primary mb-4 font-bold">Ruta Identidad</h3>
            <ul class="space-y-4 mb-8 text-sm text-on-surface-variant font-medium">
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">account_balance</span>
                <span>Recorrido guiado del Plan Fachada por el parque.</span>
              </li>
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">menu_book</span>
                <span>Visita al centro cultural José Eustasio Rivera.</span>
              </li>
              <li class="flex items-start gap-3">
                <span class="material-symbols-outlined text-secondary text-base">brush</span>
                <span>Taller interactivo en vivo con artesanos locales.</span>
              </li>
            </ul>
            <button class="w-full py-3 border border-outline-variant rounded-lg font-bold text-xs text-primary hover:bg-surface-container-low transition-colors">
              Ver Detalles
            </button>
          </div>
        </div>

      </div>
    </section>

    <!-- Interactive Map Section -->
    <section class="bg-surface-container-low py-20 px-margin-mobile md:px-margin-desktop">
      <div class="max-w-container-max mx-auto">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-gutter items-center">
          
          <div class="lg:col-span-4 space-y-8">
            <div>
              <span class="text-xs font-bold text-secondary uppercase tracking-widest block mb-2">Itinerario Visual</span>
              <h2 class="font-display text-3xl text-primary font-bold">Mapa de Experiencias</h2>
              <p class="text-on-surface-variant text-sm mt-3 leading-relaxed">
                Interactúa con los puntos de interés más importantes del municipio para planificar tu ruta perfecta.
              </p>
            </div>
            
            <div class="space-y-4">
              <div 
                v-for="(loc, key) in locations"
                :key="key"
                @click="selectedLocation = key"
                class="flex items-start gap-4 p-4 rounded-xl border-l-4 shadow-sm cursor-pointer hover:translate-x-1 transition-all"
                :class="selectedLocation === key 
                  ? 'bg-white border-primary shadow-md' 
                  : 'bg-white/40 border-outline-variant hover:bg-white/70'"
              >
                <span class="material-symbols-outlined text-primary mt-0.5">location_on</span>
                <div>
                  <h4 class="font-bold text-sm text-primary">{{ loc.title }}</h4>
                  <p class="text-xs text-on-surface-variant mt-0.5">{{ loc.sub }}</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Simulated Map Visualizer -->
          <div class="lg:col-span-8 relative min-h-[450px] md:h-[500px] bg-surface-variant rounded-2xl overflow-hidden shadow-inner border border-outline-variant/30 flex flex-col justify-end">
            <!-- Simulated Map Background -->
            <div class="absolute inset-0 bg-cover bg-center opacity-70 grayscale hover:grayscale-0 transition-all duration-700" style="background-image: url('https://lh3.googleusercontent.com/aida-public/AB6AXuDCWEsFGp7AkdBR7hPkl09cXU-jjr-UDQsAyz47_jrfZqEWW5rrHNCo1FlTCz7h3Gzx_pT552Rb7ldxFrCO8GrzJ9pKAbtbdBNvaIo5mI6UIh9yoVEwE0IK1AP4JCVkNmjip0ChV-ZL1j7SRrvjNqEnSzgLgKyshnWYSxacIuzqEdz0WK1LaBuv6JYDhRA_ZWabmeNQs3PgOsQiPQfQEfTZQXYO2dEzpsBXNxZwj_zUb20vdgn8UTznkTU3TfNmcaByCiqYWCVXpBQ')"></div>
            
            <!-- Map Pin Overlay based on Selection -->
            <div class="absolute transition-all duration-500 text-secondary animate-bounce" :class="locations[selectedLocation].coords">
              <span class="material-symbols-outlined text-4xl" style="font-variation-settings: 'FILL' 1;">location_on</span>
            </div>

            <!-- Details Panel Overlay -->
            <div class="relative z-10 p-6 md:p-8 bg-white/95 backdrop-blur-md rounded-t-2xl border-t border-outline-variant/30 m-4 rounded-xl shadow-lg">
              <h3 class="font-display text-lg text-primary font-bold mb-1">
                {{ locations[selectedLocation].title }}
              </h3>
              <p class="text-xs text-secondary font-bold uppercase tracking-wider mb-3">
                {{ locations[selectedLocation].sub }}
              </p>
              <p class="text-on-surface-variant text-sm leading-relaxed">
                {{ locations[selectedLocation].desc }}
              </p>
            </div>
          </div>

        </div>
      </div>
    </section>

    <!-- Travel Tips -->
    <section class="py-20 px-margin-mobile md:px-margin-desktop max-w-container-max mx-auto">
      <h2 class="font-display text-3xl text-primary text-center mb-16 font-bold">Consejos prácticos para tu viaje</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-gutter">
        
        <div class="p-8 bg-surface rounded-xl border border-outline-variant hover:border-primary transition-colors flex flex-col justify-between">
          <div>
            <span class="material-symbols-outlined text-secondary text-3xl mb-4">thermostat</span>
            <h3 class="font-display text-lg text-primary mb-3 font-bold">Clima</h3>
            <p class="text-on-surface-variant text-sm leading-relaxed">
              Temperatura promedio de 24°C. Clima templado y agradable durante todo el año, ideal para caminatas al aire libre y baños termales nocturnos.
            </p>
          </div>
        </div>

        <div class="p-8 bg-surface rounded-xl border border-outline-variant hover:border-primary transition-colors flex flex-col justify-between">
          <div>
            <span class="material-symbols-outlined text-secondary text-3xl mb-4">backpack</span>
            <h3 class="font-display text-lg text-primary mb-3 font-bold">Qué Llevar</h3>
            <p class="text-on-surface-variant text-sm leading-relaxed">
              Ropa cómoda y ligera, zapatos antideslizantes para trekking, traje de baño para los termales, bloqueador solar y repelente de insectos biodegradable.
            </p>
          </div>
        </div>

        <div class="p-8 bg-surface rounded-xl border border-outline-variant hover:border-primary transition-colors flex flex-col justify-between">
          <div>
            <span class="material-symbols-outlined text-secondary text-3xl mb-4">directions_bus</span>
            <h3 class="font-display text-lg text-primary mb-3 font-bold">Cómo Llegar</h3>
            <p class="text-on-surface-variant text-sm leading-relaxed">
              Desde Neiva, toma un autobús de transporte público local (20 minutos) o un taxi. La vía principal está totalmente pavimentada y en excelente estado.
            </p>
          </div>
        </div>

      </div>
    </section>

    <!-- Final CTA Section -->
    <section class="py-20 bg-primary-container text-on-primary-container">
      <div class="px-margin-mobile max-w-4xl mx-auto text-center">
        <h2 class="font-display text-3xl md:text-4xl text-white mb-6 font-bold">¿Listo para vivir la tradición?</h2>
        <p class="font-body text-base md:text-lg mb-10 opacity-90 max-w-xl mx-auto leading-relaxed">
          Nuestros guías locales certificados están disponibles para personalizar tu estancia y acompañarte.
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <a 
            href="https://wa.me/573000000000?text=Hola,%20quisiera%20planificar%20un%20viaje%20a%20Rivera" 
            target="_blank" 
            class="bg-secondary text-on-secondary px-8 py-4 rounded-full font-bold text-xs flex items-center justify-center gap-3 hover:translate-y-[-2px] transition-all shadow-md"
          >
            <span class="material-symbols-outlined text-sm">chat</span>
            Contactar Guía Local (WhatsApp)
          </a>
          <button 
            @click="$bus?.emit('open-booking')"
            class="bg-white text-primary px-8 py-4 rounded-full font-bold text-xs flex items-center justify-center gap-3 hover:translate-y-[-2px] transition-all shadow-md"
          >
            <span class="material-symbols-outlined text-sm">event_available</span>
            Reservar Ahora
          </button>
        </div>
      </div>
    </section>
  </div>
</template>
