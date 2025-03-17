<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Nav from './components/Nav.vue'
import Experience from './views/Experience.vue'
import HomeView from './views/HomeView.vue'
// import Stats from './views/Stats.vue'
import Projects from './views/Projects.vue'
import Contact from './views/Contact.vue'
import Footer from './components/Footer.vue'
import Spotlight from './components/Spotlight.vue'

</script>

<template>
  <Spotlight />
  <Nav />
  <div class="content">
    <HomeView />
    <Experience />
    <!-- <Stats /> -->
    <Projects />
    <Contact />
    <Footer />
  </div>
</template>

<style scoped>
  .content {
    width: 50%;
    display: flex;
    flex-direction: column;
    gap: 8rem;
  }

  @media only screen and (max-width: 1280px) {
    .content {
      width: 100%;
    }
  
  }
</style>
