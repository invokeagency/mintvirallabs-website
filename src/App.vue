<template>
  <div class="app">
    <HeaderSection />
    <FeaturedOn />
    <HowItWorks />
    <TeamSection />
    <WhyUs />
    <FAQ />
    <ApplicationForm />
  </div>
</template>

<script>
import HeaderSection from './components/Header.vue'
import FeaturedOn from './components/FeaturedOn.vue'
import HowItWorks from './components/HowItWorks.vue'
import TeamSection from './components/Team.vue'
import WhyUs from './components/WhyUs.vue'
import FAQ from './components/FAQ.vue'
import ApplicationForm from './components/ApplicationForm.vue'

export default {
  name: 'App',
  components: {
    HeaderSection,
    FeaturedOn,
    HowItWorks,
    TeamSection,
    WhyUs,
    FAQ,
    ApplicationForm
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap');
@import './assets/styles/main.scss';

.app {
  min-height: 100vh;
}
</style>
