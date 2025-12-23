<template>
  <div class="min-h-screen bg-linear-to-br from-gray-900
   via-blue-900 to-gray-900">
    <Navbar></Navbar>
    <About></About>
    <Certificates></Certificates>
    <Skills></Skills>
    <Projects></Projects>
    <Contact></Contact>
  </div>
</template>

<script setup>
import Navbar from "./components/Navbar.vue";
import About from "./components/About.vue";
import Skills from "./components/Skills.vue";
import Projects from "./components/Projects.vue";
import Contact from "./components/Contact.vue";
import Certificates from "./components/Certificates.vue";

import { onMounted } from "vue";
import Aos from "aos";
import "aos/dist/aos.css";

onMounted(() => {
  Aos.init({
    duration: 100,
    easing: "ease-in-out",
    once: false,
    offset: 100,
  });
});

</script>

<style scoped></style>
