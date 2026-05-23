<template>
  <footer class="bg-surface-container-highest dark:bg-surface-container-low w-full mt-auto border-t border-outline-variant dark:border-outline">
    <div class="grid grid-cols-1 md:grid-cols-4 gap-gutter px-margin-mobile md:px-margin-desktop py-12 max-w-container-max mx-auto">
      <div class="col-span-1 md:col-span-1">
        <h3 class="font-display text-2xl text-primary mb-4 font-bold">Rivera Huila</h3>
        <p class="text-on-surface-variant font-body text-sm mb-6">Equilibrio perfecto entre arquitectura colonial, bienestar termal y exuberante naturaleza.</p>
        <div class="flex gap-4">
          <a class="text-primary hover:scale-110 transition-transform p-2 bg-surface rounded-full shadow-sm" href="#" aria-label="Social">
            <span class="material-symbols-outlined">social_leaderboard</span>
          </a>
          <a class="text-primary hover:scale-110 transition-transform p-2 bg-surface rounded-full shadow-sm" href="#" aria-label="Share">
            <span class="material-symbols-outlined">share</span>
          </a>
          <a class="text-primary hover:scale-110 transition-transform p-2 bg-surface rounded-full shadow-sm" href="#" aria-label="Photos">
            <span class="material-symbols-outlined">photo_camera</span>
          </a>
        </div>
      </div>
      <div>
        <h4 class="font-bold text-xs text-on-surface uppercase mb-6 tracking-wider">Explora</h4>
        <ul class="space-y-4">
          <li>
            <NuxtLink class="text-on-surface-variant hover:text-primary transition-all font-body text-sm hover:underline" to="/lugares">Atractivos</NuxtLink>
          </li>
          <li>
            <NuxtLink class="text-on-surface-variant hover:text-primary transition-all font-body text-sm hover:underline" to="/directorio">Directorio Local</NuxtLink>
          </li>
          <li>
            <NuxtLink class="text-on-surface-variant hover:text-primary transition-all font-body text-sm hover:underline" to="/agenda">Agenda Cultural</NuxtLink>
          </li>
          <li>
            <NuxtLink class="text-on-surface-variant hover:text-primary transition-all font-body text-sm hover:underline" to="/planifica">Organizar Viaje</NuxtLink>
          </li>
        </ul>
      </div>
      <div>
        <h4 class="font-bold text-xs text-on-surface uppercase mb-6 tracking-wider">Institucional</h4>
        <ul class="space-y-4">
          <li><a class="text-on-surface-variant hover:text-primary transition-all font-body text-sm hover:underline" href="#">Alcaldía de Rivera</a></li>
          <li><a class="text-on-surface-variant hover:text-primary transition-all font-body text-sm hover:underline" href="#">Privacidad</a></li>
          <li><a class="text-on-surface-variant hover:text-primary transition-all font-body text-sm hover:underline" href="#">Términos y Condiciones</a></li>
          <li><a class="text-on-surface-variant hover:text-primary transition-all font-body text-sm hover:underline" href="#">Contacto</a></li>
        </ul>
      </div>
      <div>
        <h4 class="font-bold text-xs text-on-surface uppercase mb-6 tracking-wider">Contacto</h4>
        <p class="text-on-surface-variant font-body text-sm mb-2">Carrera 4 # 3-21, Centro Histórico</p>
        <p class="text-on-surface-variant font-body text-sm mb-2">Rivera, Huila - Colombia</p>
        <p class="text-on-surface-variant font-body text-sm">info@riveraturistica.gov.co</p>
      </div>
    </div>
    <div class="px-margin-mobile md:px-margin-desktop py-8 border-t border-outline-variant max-w-container-max mx-auto flex flex-col md:flex-row justify-between items-center gap-4">
      <p class="text-on-surface-variant font-body text-xs">© 2026 Alcaldía de Rivera. Todos los derechos reservados.</p>
      <div class="flex items-center gap-2 text-on-surface-variant text-xs">
        <span class="material-symbols-outlined text-base">verified</span>
        Portal Oficial de Turismo de Rivera, Huila
      </div>
    </div>
  </footer>
</template>
