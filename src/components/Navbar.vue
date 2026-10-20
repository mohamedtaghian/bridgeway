<script setup>
import arrowRight from '@/assets/svg/arrow-right.svg'

function scrollTo(selector) {
  if (!selector || selector === '#') {
    window.scrollTo({ top: 0, behavior: 'smooth' })
    if (window.location.hash) {
      history.pushState(null, '', window.location.pathname)
    }
    return
  }
  const el = document.querySelector(selector)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
    history.pushState(null, '', selector)
  }
}
</script>

<template>
  <header class="z-30 relative flex items-center lg:px-[120px] max-w-[1440px] min-h-[112px]">
    <!-- Desktop and Tablet Navigation  -->
    <nav class="hidden md:flex flex-1 justify-between items-center">
      <div class="flex items-center gap-12 lg:gap-20">
        <!-- Brand Logo -->
        <a
          href="#"
          @click.prevent="scrollTo('#')"
          class="hover:opacity-90 focus:outline-none focus-visible:ring-2 focus-visible:ring-brand-yellow font-general font-bold text-[32px] text-white tracking-[-4%] transition-opacity duration-200"
        >
          Bridgeway
        </a>

        <!-- Desktop Nav Links -->
        <ul class="flex items-center gap-[80px]">
          <li>
            <a
              href="#benefits"
              @click.prevent="scrollTo('#benefits')"
              class="focus:outline-none focus-visible:ring-2 focus-visible:ring-brand-yellow font-sans font-medium text-[20px] text-white hover:text-brand-yellow transition-colors duration-200 cursor-pointer"
            >
              Benefits
            </a>
          </li>
          <li>
            <a
              href="#contact"
              @click.prevent="scrollTo('#contact')"
              class="focus:outline-none focus-visible:ring-2 focus-visible:ring-brand-yellow font-sans font-medium text-[20px] text-white hover:text-brand-yellow transition-colors duration-200 cursor-pointer"
            >
              Contact Us
            </a>
          </li>
        </ul>
      </div>

      <!-- Desktop CTA Button -->
      <a
        href="#contact"
        @click.prevent="scrollTo('#contact')"
        class="group inline-flex items-center gap-3 bg-brand-yellow shadow-sm hover:shadow-md px-7 py-2 rounded-full focus:outline-none focus-visible:ring-2 focus-visible:ring-white font-sans font-semibold text-[20px] text-brand-dark hover:scale-[1.03] active:scale-95 transition-all duration-300 cursor-pointer"
      >
        <span>Get Started</span>
        <img
          :src="arrowRight"
          class="transition-transform group-hover:translate-x-1 duration-300 s-4"
        />
      </a>
    </nav>

    <!-- Mobile Navigation  -->
    <nav class="md:hidden flex flex-col gap-4 w-full">
      <!--  Logo and CTA -->
      <div class="flex justify-between items-center">
        <a
          href="#"
          @click.prevent="scrollTo('#')"
          class="font-general font-bold text-[20px] text-white tracking-[-4%]"
        >
          Bridgeway
        </a>

        <a
          href="#contact"
          @click.prevent="scrollTo('#contact')"
          class="group inline-flex items-center gap-2 bg-brand-yellow shadow-sm px-4 py-2 rounded-full font-sans font-semibold text-brand-dark text-base active:scale-95 transition-all duration-200 cursor-pointer"
        >
          <span>Get Started</span>
          <img
            :src="arrowRight"
            class="transition-transform group-hover:translate-x-0.5 duration-200 s-[20px]"
          />
        </a>
      </div>

      <!-- Mobile Links Bar -->
      <ul class="flex items-center gap-6 pt-1">
        <li>
          <a
            href="#benefits"
            @click.prevent="scrollTo('#benefits')"
            class="font-sans font-medium text-white hover:text-brand-yellow transition-colors duration-200 cursor-pointer"
          >
            Benefits
          </a>
        </li>
        <li>
          <a
            href="#contact"
            @click.prevent="scrollTo('#contact')"
            class="font-sans font-medium text-white hover:text-brand-yellow transition-colors duration-200 cursor-pointer"
          >
            Contact Us
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>
