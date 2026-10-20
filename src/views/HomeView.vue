<script setup>
import HeroSection from '@/components/HeroSection.vue'
import LogoTicker from '@/components/LogoTicker.vue'
import BenefitsSection from '@/components/BenefitsSection.vue'
import CtaSection from '@/components/CtaSection.vue'
import FooterSection from '@/components/FooterSection.vue'
</script>

<template>
  <main class="bg-white min-h-screen">
    <!-- Hero Section -->
    <HeroSection />

    <!-- Partner Logos -->
    <LogoTicker />

    <!-- Benefits Section -->
    <BenefitsSection />

    <!-- Ready to Cross Over Section -->
    <CtaSection />

    <!-- Footer Section -->
    <FooterSection />
  </main>
</template>
