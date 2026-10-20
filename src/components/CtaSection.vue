<script setup>
import posTerminalImg from '@/assets/images/pos-terminal.jpg'
import ctaArchShape from '@/assets/svg/cta-arch-shape.svg'
import arrowRight from '@/assets/svg/arrow-right.svg'

function handleGetStarted() {
  const el = document.getElementById('contact')
  if (el) {
    el.scrollIntoView({ behavior: 'smooth' })
    history.pushState(null, '', '#contact')
  }
}
</script>

<template>
  <section class="relative bg-white pb-20 w-full overflow-hidden">
    <!-- DESKTOP CTA -->
    <div class="hidden lg:block relative mx-auto px-12 lg:px-20 max-w-[1440px] min-h-[874px]">
      <!-- Right Yellow Arch -->
      <div class="top-[120px] left-[763px] z-0 absolute w-[580px] h-[517px]">
        <img :src="ctaArchShape" class="w-full h-auto object-contain" />
      </div>

      <!-- Left: POS Terminal Photography -->
      <div
        class="top-[120px] left-[80px] absolute rounded-[30px] max-w-[648px] h-[450px] overflow-hidden"
      >
        <img
          :src="posTerminalImg"
          alt="Seamless card payment with terminal"
          class="w-full h-full object-cover"
        />
      </div>

      <!-- Center: Floating Brand CTA Card -->
      <div
        class="top-[438px] left-[493px] z-20 absolute flex flex-col gap-6 bg-brand-dark p-[40px] rounded-[40px] max-w-[600px]"
      >
        <h2 id="cta-heading" class="font-general font-bold text-[40px] text-white tracking-[-2%]">
          Ready to cross over to<br /><span class="text-brand-yellow">better payments?</span>
        </h2>

        <p class="max-w-[370px] font-sans font-normal text-white/80 text-xl leading-[150%]">
          Get set up in minutes. No hidden fees, no long contracts.
        </p>

        <a
          href="#contact"
          @click.prevent="handleGetStarted"
          class="group inline-flex items-center gap-3 bg-brand-yellow shadow-md hover:shadow-lg px-6 py-2 rounded-full focus:outline-none focus-visible:ring-4 focus-visible:ring-white w-fit font-sans font-semibold text-dark text-xl hover:scale-[1.03] active:scale-95 transition-all duration-300 cursor-pointer"
        >
          <span>Get Started</span>
          <img
            :src="arrowRight"
            alt=""
            class="size-4 transition-transform group-hover:translate-x-1 duration-300"
          />
        </a>
      </div>
    </div>

    <!-- TABLET CTA -->
    <div class="hidden lg:hidden md:block mx-auto px-8 max-w-2xl">
      <div
        class="flex flex-col gap-6 bg-brand-dark shadow-xl mb-8 p-10 rounded-[36px] sm:text-left text-center"
      >
        <h2
          class="font-general font-bold text-brand-yellow text-3xl sm:text-4xl leading-tight tracking-[-2%]"
        >
          Ready to cross over to<br />better payments?
        </h2>
        <p class="max-w-lg font-sans text-white/80 text-lg leading-relaxed">
          Get set up in minutes. No hidden fees, no long contracts.
        </p>

        <a
          href="#contact"
          @click.prevent="handleGetStarted"
          class="group inline-flex items-center gap-3 bg-brand-yellow shadow-md px-7 py-3 rounded-full w-fit font-sans font-semibold text-dark text-base hover:scale-[1.03] active:scale-95 transition-all duration-300 cursor-pointer"
        >
          <span>Get Started</span>
          <img
            :src="arrowRight"
            alt=""
            class="size-4 transition-transform group-hover:translate-x-1 duration-300"
          />
        </a>
      </div>

      <div class="shadow-lg border border-black/5 rounded-[28px] w-full h-80 overflow-hidden">
        <img
          :src="posTerminalImg"
          alt="Payment terminal in use"
          class="w-full h-full object-cover"
          loading="lazy"
        />
      </div>
    </div>

    <!-- MOBILE CTA -->
    <div class="md:hidden flex flex-col gap-6 mx-auto px-5 py-8">
      <!-- Mobile CTA Card -->
      <div class="flex flex-col gap-8 bg-brand-dark p-8 rounded-[32px]">
        <h2 class="font-general font-bold text-[32px] text-brand-yellow leading-[105%]">
          Ready to cross over to<br />better payments?
        </h2>

        <p class="font-sans text-white/80 leading-[145%]">
          Get set up in minutes. No hidden fees, no long contracts.
        </p>

        <a
          href="#contact"
          @click.prevent="handleGetStarted"
          class="group inline-flex items-center gap-3 bg-brand-yellow shadow-md px-4 py-2 rounded-full w-fit font-sans font-semibold text-dark active:scale-95 transition-all duration-200 cursor-pointer"
        >
          <span>Get Started</span>
          <img
            :src="arrowRight"
            alt=""
            class="size-3.5 transition-transform group-hover:translate-x-0.5 duration-200"
          />
        </a>
      </div>

      <!-- Mobile POS Photo -->
      <div class="rounded-[24px] w-full h-[220px] overflow-hidden">
        <img
          :src="posTerminalImg"
          alt="In-person payment processing"
          class="w-full h-full object-cover"
        />
      </div>
    </div>
  </section>
</template>
