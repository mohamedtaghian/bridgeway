<script setup>
import logoGoogle from '@/assets/svg/logo-google.svg'
import logoAdobe from '@/assets/svg/logo-adobe.svg'
import logoStripe from '@/assets/svg/logo-stripe.svg'
import logoCoinbase from '@/assets/svg/logo-coinbase.svg'
import logoGithub from '@/assets/svg/logo-github.svg'
import logoUber from '@/assets/svg/logo-uber.svg'

const partnerLogos = [
  { name: 'Google', src: logoGoogle, heightClass: 'h-7 sm:h-9' },
  { name: 'Adobe', src: logoAdobe, heightClass: 'h-6 sm:h-8' },
  { name: 'Stripe', src: logoStripe, heightClass: 'h-7 sm:h-9' },
  { name: 'Coinbase', src: logoCoinbase, heightClass: 'h-6 sm:h-8' },
  { name: 'GitHub', src: logoGithub, heightClass: 'h-7 sm:h-9' },
  { name: 'Uber', src: logoUber, heightClass: 'h-6 sm:h-8' },
]
</script>

<template>
  <div class="relative bg-white py-8 sm:py-12 md:py-16 w-full overflow-hidden select-none">
    <!-- Outer Container -->
    <div class="relative mx-auto px-5 sm:px-8 max-w-[1440px]">
      <!-- Left Edge Gradient -->
      <div
        class="top-0 bottom-0 left-0 z-10 absolute bg-gradient-to-r from-white via-white/80 to-transparent w-16 sm:w-28 md:w-40 pointer-events-none"
      ></div>

      <!-- Right Edge Gradient -->
      <div
        class="top-0 right-0 bottom-0 z-10 absolute bg-gradient-to-l from-white via-white/80 to-transparent w-16 sm:w-28 md:w-40 pointer-events-none"
      ></div>

      <!-- Scrolling Marquee Track -->
      <div class="group flex overflow-hidden">
        <!-- Track 1 -->
        <div
          class="flex flex-shrink-0 items-center gap-12 sm:gap-16 md:gap-24 pr-12 sm:pr-16 md:pr-24 animate-[marquee_28s_linear_infinite] group-hover:[animation-play-state:paused]"
        >
          <div
            v-for="logo in partnerLogos"
            :key="logo.name"
            class="flex justify-center items-center opacity-70 hover:opacity-100 transition-opacity duration-300"
          >
            <img
              :src="logo.src"
              :alt="logo.name"
              :class="[logo.heightClass, 'w-auto object-contain']"
              loading="lazy"
            />
          </div>
        </div>

        <!-- Track 2 -->
        <div
          class="flex flex-shrink-0 items-center gap-12 sm:gap-16 md:gap-24 pr-12 sm:pr-16 md:pr-24 animate-[marquee_28s_linear_infinite] group-hover:[animation-play-state:paused]"
        >
          <div
            v-for="logo in partnerLogos"
            :key="'dup-' + logo.name"
            class="flex justify-center items-center opacity-70 hover:opacity-100 transition-opacity duration-300"
          >
            <img
              :src="logo.src"
              :alt="logo.name"
              :class="[logo.heightClass, 'w-auto object-contain']"
              loading="lazy"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
