<script setup>
import { ref } from 'vue'
import SiteHeader from './components/SiteHeader.vue'
import HeroSection from './components/HeroSection.vue'
import MenuSection from './components/MenuSection.vue'
import BrandStory from './components/BrandStory.vue'
import VisitSection from './components/VisitSection.vue'
import SiteFooter from './components/SiteFooter.vue'
import BookingDialog from './components/BookingDialog.vue'

const booking = ref(null)
const openBooking = () => booking.value.open()
</script>

<template>
  <div class="wrap"><SiteHeader @reserve="openBooking" /></div>
  <main>
    <div class="wrap"><HeroSection @reserve="openBooking" /><MenuSection /></div>
    <BrandStory />
    <VisitSection @reserve="openBooking" />
  </main>
  <SiteFooter />
  <BookingDialog ref="booking" />
</template>
