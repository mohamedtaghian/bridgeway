<script setup>
import socialLinkedin from '@/assets/svg/social-linkedin.svg'
import socialFacebook from '@/assets/svg/social-facebook.svg'
import socialInstagram from '@/assets/svg/social-instagram.svg'
import footerDecorDesktop from '@/assets/svg/footer-decor-desktop.svg'
import footerDecorMobile from '@/assets/svg/footer-decor-mobile.svg'

const socialLinks = [
  { name: 'LinkedIn', icon: socialLinkedin, href: 'https://linkedin.com' },
  { name: 'Facebook', icon: socialFacebook, href: 'https://facebook.com' },
  { name: 'Instagram', icon: socialInstagram, href: 'https://instagram.com' },
]

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
  if (window.location.hash) {
    history.pushState(null, '', window.location.pathname)
  }
}
</script>

<template>
  <footer
    id="contact"
    class="relative w-full max-w-[1440px] h-[347px] lg:h-[629px] overflow-hidden"
  >
    <!-- Footer Main Content  -->
    <div
      class="flex md:flex-row flex-col justify-between items-start md:items-center gap-8 md:gap-12 mx-auto px-5 max-w-[1278px]"
    >
      <!-- Left: Brand Info -->
      <div class="flex flex-col gap-3 md:gap-6">
        <a
          href="#"
          @click.prevent="scrollToTop"
          class="hover:opacity-80 focus:outline-none focus-visible:ring-2 focus-visible:ring-brand-dark font-general font-bold text-brand-text-dark md:text-[32px] text-2xl tracking-[-4%] transition-opacity cursor-pointer"
        >
          Bridgeway
        </a>
        <p class="font-sans font-normal text-black/60 md:text-[28px] text-base leading-normal">
          Everything payments, on one bridge
        </p>
      </div>

      <!-- Right: Social Links -->
      <div class="flex items-center gap-4 md:gap-[31px]">
        <a
          v-for="social in socialLinks"
          :key="social.name"
          :href="social.href"
          target="_blank"
          rel="noopener noreferrer"
          class="group flex justify-center items-center hover:bg-brand-light/50 focus:outline-none focus-visible:ring-2 focus-visible:ring-brand-dark w-12 sm:w-14 lg:w-16 h-12 sm:h-14 lg:h-16 hover:scale-105 active:scale-95 transition-all duration-300"
        >
          <img
            :src="social.icon"
            :alt="social.name"
            class="size-[48px] md:size-[64px] group-hover:scale-110 transition-transform duration-300"
          />
        </a>
      </div>
    </div>

    <!-- Bottom Decore -->
    <div class="-bottom-[20%] absolute flex justify-center items-end w-full">
      <!-- Desktop Decore -->
      <img
        :src="footerDecorDesktop"
        class="hidden lg:block w-full max-w-[1283px] h-auto object-bottom object-contain"
      />

      <!-- Mobile Decore -->
      <img
        :src="footerDecorMobile"
        class="lg:hidden block mb-2 w-full max-w-[315px] h-auto object-bottom object-contain"
      />
    </div>
  </footer>
</template>
