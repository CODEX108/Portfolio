<script setup lang="ts">
  import { nextTick, onMounted, ref } from 'vue';

  import Loader from './components/loader/Loader.vue';
  import NavBar from './components/navbar/NavBar.vue';
  import Hero from './components/hero/Hero.vue';
  import Work from './components/work/Work.vue';
  import Marquee from './components/marquee/Marquee.vue';
  import SideProjects from './components/side-projects/SideProjects.vue';
  import Contact from './components/contact/Contact.vue';
  import Mouse from './components/mouse/Mouse.vue';
  import Achievements from './components/achievements/Achievements.vue';

  const loaded = ref(false);
  const isSafari = /^((?!chrome|android).)*safari/i.test(navigator.userAgent);

  onMounted(async () => {
    await nextTick();
    setTimeout(() => {
      loaded.value = true;
    }, 2000);
  });
</script>

<template>
  <Loader :loaded="loaded" />
  <NavBar />
  <Hero />
  <Marquee title="work" emoji="." />
  <Work ref="scrollRef" />
  <Marquee title="projects" emoji="." />
  <SideProjects />
  <Marquee title="achievements" emoji="." />
  <Achievements ref="scrollRef" />
  <Contact />
  <Mouse v-if="!isSafari" />
  <div id="grain-overlay"></div>
</template>

<style>
  #grain-overlay {
    background-image: url('/images/noise/noise.webp');
    position: fixed;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%);
    -ms-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    height: 100vh;
    width: 100vw;
    z-index: 999;
    pointer-events: none;
  }
</style>