<script setup>
import Navbar from '@/components/Navbar.vue'
import heroBridgeVector from '@/assets/svg/hero-bridge-vector.svg'
import heroPurpleBg from '@/assets/svg/hero-purple-shape.svg'
import heroYellowBg from '@/assets/svg/hero-yellow-bg.svg'
import arrowUpRight from '@/assets/svg/arrow-up-right.svg'
import heroBridgeImg from '@/assets/images/hero-bridge.jpg'

function scrollTo(selector) {
  const el = document.querySelector(selector)
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
    history.pushState(null, '', selector)
  }
}
</script>

<template>
  <section>
    <!-- DESKTOP HERO -->
    <div class="hidden lg:block relative bg-white min-h-[785px]">
      <!-- Navbar -->
      <Navbar />

      <!-- Purple Curve -->
      <div class="top-0 left-[60px] z-20 absolute w-[1309px]">
        <img :src="heroPurpleBg" />
      </div>

      <!-- Yellow Curve -->
      <div class="top-0.5 left-[441px] z-10 absolute rounded-[76px] w-[879px] h-[735px]">
        <img :src="heroYellowBg" />
      </div>

      <!-- Bridge Image -->
      <div class="top-[246px] left-[149.14px] z-20 absolute w-[1230.6px] h-[169.33px]">
        <img :src="heroBridgeVector" />
      </div>

      <!-- Hero Content Container -->
      <div class="top-[498px] left-[242px] z-40 absolute mx-auto">
        <!-- Main Headline -->
        <h1 class="flex gap-[56px] h-[70px] font-general font-bold text-[70px] tracking-[-4%]">
          <span class="text-brand-yellow">Your way to </span>
          <span class="text-brand-dark">better payments</span>
        </h1>

        <!-- Subtext -->
        <p
          class="mt-8 xl:mt-12 mr-[12%] xl:mr-[14%] ml-auto max-w-[372px] h-[84px] font-sans font-normal text-[28px] text-black/80 leading-[150%]"
        >
          Accept, send, and reconcile payments in one place.
        </p>
      </div>

      <!-- Up-Right CTA Button -->
      <div class="top-[601px] left-[1184px] z-30 absolute">
        <a
          href="#benefits"
          @click.prevent="scrollTo('#benefits')"
          class="group flex justify-center items-center bg-brand-dark shadow-xl hover:shadow-2xl rounded-[60px] focus:outline-none focus-visible:ring-4 focus-visible:ring-brand-yellow size-[160px] hover:scale-105 active:scale-95 transition-all duration-300 cursor-pointer"
        >
          <img
            :src="arrowUpRight"
            alt=""
            class="size-[64px] transition-transform group-hover:-translate-y-1.5 group-hover:translate-x-1.5 duration-300"
          />
        </a>
      </div>
    </div>

    <!-- TABLET HERO -->
    <div
      class="hidden lg:hidden md:block relative bg-brand-dark px-8 pt-6 pb-16 rounded-b-[60px] w-full overflow-hidden"
    >
      <!-- Tablet Navbar -->
      <Navbar class="mb-12" />

      <div class="z-10 relative flex flex-col gap-8 mx-auto max-w-2xl">
        <h1 class="font-general font-bold text-brand-yellow text-5xl leading-[1.1] tracking-[-4%]">
          Your way to <span class="text-white">better payments</span>
        </h1>

        <p class="max-w-lg font-sans text-white text-xl leading-relaxed">
          Accept, send, and reconcile payments in one place.
        </p>

        <div class="flex justify-between items-center gap-6 pt-4">
          <!-- Thumbnail bridge image -->
          <div class="shadow-lg border border-white/10 rounded-[32px] w-64 h-56 overflow-hidden">
            <img
              :src="heroBridgeImg"
              alt="Bridge payment connectivity"
              class="w-full h-full object-cover"
            />
          </div>

          <!-- Tablet arrow button -->
          <a
            href="#benefits"
            @click.prevent="scrollTo('#benefits')"
            class="group flex justify-center items-center bg-brand-yellow shadow-lg rounded-full hover:scale-105 active:scale-95 transition-all duration-300 cursor-pointer s-24"
          >
            <img
              :src="arrowUpRight"
              alt=""
              class="brightness-0 transition-transform group-hover:-translate-y-1 group-hover:translate-x-1 duration-300 s-10 filter"
            />
          </a>
        </div>
      </div>
    </div>

    <!-- Mobile Hero -->
    <div
      class="md:hidden block relative bg-brand-dark px-5 pt-4 pb-10 rounded-b-[40px] w-full overflow-hidden"
    >
      <!-- Navbar -->
      <Navbar class="mb-8 px-0" />

      <!-- Hero Content-->
      <div class="flex flex-col gap-4">
        <h1 class="font-inter font-bold text-[36px] text-brand-yellow leading-[105%]">
          Your way to<br />better payments
        </h1>
        <p class="font-sans text-white/80 text-base">
          Accept, send, and reconcile payments in one place.
        </p>
      </div>

      <!-- Mobile Hero Bottom Row  -->
      <div class="flex justify-between items-end gap-4 mt-8">
        <!-- Payment Photo Thumbnail -->
        <div
          class="flex-shrink-0 shadow-md rounded-[32px] w-[200px] sm:w-[220px] h-[200px] sm:h-[220px] overflow-hidden"
        >
          <img
            :src="heroBridgeImg"
            alt="Seamless payments across borders"
            class="w-full h-full object-cover"
            loading="eager"
          />
        </div>

        <!-- Mobile Up-Right Arrow Button -->
        <a
          href="#benefits"
          @click.prevent="scrollTo('#benefits')"
          class="group flex justify-center items-center bg-transparent p-4 active:scale-95 transition-transform duration-200 cursor-pointer"
        >
          <img
            :src="arrowUpRight"
            alt=""
            class="w-16 sm:w-20 h-16 sm:h-20 transition-transform group-hover:-translate-y-1 group-hover:translate-x-1 duration-200"
          />
        </a>
      </div>
    </div>
  </section>
</template>
