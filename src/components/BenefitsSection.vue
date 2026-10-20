<script setup>
import iconAccept from '@/assets/svg/icon-accept-payments.svg'
import iconReconcile from '@/assets/svg/icon-reconcile.svg'
import iconPayouts from '@/assets/svg/icon-send-payouts.svg'
import iconSecure from '@/assets/svg/icon-secure.svg'
import iconReporting from '@/assets/svg/icon-reporting.svg'
import iconDevelopers from '@/assets/svg/icon-developers.svg'

const benefits = [
  {
    id: 1,
    title: 'Accept Payments',
    description:
      'Take cards, wallets, and bank transfers online and in person through a single integration.',
    icon: iconAccept,
    isDark: true,
  },
  {
    id: 2,
    title: 'Reconcile automatically',
    description:
      'Every transaction is matched to your books in real time, so month-end stops being a chore.',
    icon: iconReconcile,
    isDark: false,
  },
  {
    id: 3,
    title: 'Send Payouts',
    description: 'Pay suppliers, partners, and staff in minutes, in bulk or one at a time.',
    icon: iconPayouts,
    isDark: true,
  },
  {
    id: 4,
    title: 'Secure by default',
    description:
      'Built-in fraud checks, encryption, and identity verification protect every payment.',
    icon: iconSecure,
    isDark: false,
  },
  {
    id: 5,
    title: 'Clear reporting',
    description: "Live dashboards show where your money is, what's settled, and what's pending.",
    icon: iconReporting,
    isDark: true,
  },
  {
    id: 6,
    title: 'Built for developers',
    description:
      'Clean APIs, sandbox testing, and webhooks help your team ship in days, not months.',
    icon: iconDevelopers,
    isDark: false,
  },
]
</script>

<template>
  <section
    id="benefits"
    class="bg-white mx-auto px-5 sm:px-8 md:px-12 lg:px-20 py-16 sm:py-20 md:py-28 w-full max-w-[1440px]"
  >
    <!-- Header Section -->
    <div
      class="flex lg:flex-row flex-col lg:justify-between lg:items-start gap-6 lg:gap-16 mb-12 sm:mb-16 md:mb-20"
    >
      <!-- Section Title -->
      <h2
        id="benefits-title"
        class="max-w-md font-general font-bold text-[36px] text-brand-dark lg:text-[40px] leading-[105%] lg:leading-[100%] lg:tracking-[-4%]"
      >
        Everything payments,<br class="hidden sm:inline" />
        on one bridge
      </h2>

      <!-- Section Intro Text -->
      <p
        class="max-w-xl font-sans font-normal text-black/80 lg:text-[28px] text-lg lg:text-xl leading-[145%] lg:leading-[150%]"
      >
        One platform connects you to customers, banks, and your own books, so money moves without
        the friction.
      </p>
    </div>

    <!-- 6 Benefits Grid  -->
    <div class="gap-5 sm:gap-6 lg:gap-8 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
      <article
        v-for="item in benefits"
        :key="item.id"
        class="group relative flex flex-col justify-between hover:shadow-xl p-6 sm:p-8 md:p-10 rounded-[32px] md:rounded-[40px] focus-within:ring-2 focus-within:ring-brand-yellow transition-all hover:-translate-y-2 duration-300"
        :class="[
          item.isDark
            ? 'bg-brand-dark text-white'
            : 'bg-white text-brand-dark border border-brand-border',
        ]"
      >
        <!-- Icon -->
        <div
          class="flex justify-center items-center mb-8 sm:mb-12 rounded-[24px] w-16 md:w-[72px] h-16 md:h-[72px] group-hover:scale-105 transition-transform duration-300"
          :class="[item.isDark ? 'bg-brand-yellow' : 'bg-brand-dark']"
        >
          <img :src="item.icon" class="w-7 md:w-8 h-7 md:h-8" />
        </div>

        <!-- Content -->
        <div class="flex flex-col gap-3 md:gap-4">
          <h3
            class="font-general font-semibold md:text-[24px] text-xl sm:text-2xl leading-[150%]"
            :class="item.isDark ? 'text-white' : 'text-brand-dark'"
          >
            {{ item.title }}
          </h3>
          <p
            class="font-sans font-normal text-sm sm:text-base leading-relaxed"
            :class="item.isDark ? 'text-white/80' : 'text-brand-dark/80'"
          >
            {{ item.description }}
          </p>
        </div>
      </article>
    </div>
  </section>
</template>
