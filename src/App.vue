<template>
  <div>
    <HeroSection />
    <FeatureGrid />
    <ContactTable />
    <PricingSection />
    <StatsCounter />
    <Footer />
  </div>
</template>

<script>
import HeroSection from './components/HeroSection.vue'
import FeatureGrid from './components/FeatureGrid.vue'
import ContactTable from './components/ContactTable.vue'
import PricingSection from './components/PricingSection.vue'
import StatsCounter from './components/StatsCounter.vue'
import Footer from './components/Footer.vue'


export default {
  name: 'App',

  components: {
    HeroSection,
    FeatureGrid,
    ContactTable,
    PricingSection,
    StatsCounter,
    Footer
  },
}
</script>