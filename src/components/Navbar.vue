<template>
  <header dir="rtl"
    class="fixed top-0 w-full z-50 flex justify-between items-center p-6 bg-opacity-50 backdrop-blur-md">
    <!-- الاسم / اللوجو -->
    <div
      class="text-3xl md:text-4xl font-extrabold bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent font-sans">
      محمد <span class="font-black">مسعود</span>
    </div>

    <!-- زر الهامبرغر للـ Mobile -->
    <div class="md:hidden z-50">
      <button type="button"
        class="block p-2 rounded-lg bg-blue-800/50 hover:bg-blue-700/50 transition-all duration-300 focus:outline-none"
        @click="isMenuOpen = !isMenuOpen">
        <div class="relative w-6 h-6">
          <span :class="[
            'absolute left-0 w-6 h-0.5 bg-blue-200 transition-all duration-300',
            isMenuOpen ? 'rotate-45 top-3' : 'top-1',
          ]"></span>
          <span :class="[
            'absolute left-0 w-6 h-0.5 bg-blue-200 transition-all duration-300',
            isMenuOpen ? 'opacity-0' : 'top-3 opacity-100',
          ]"></span>
          <span :class="[
            'absolute left-0 w-6 h-0.5 bg-blue-200 transition-all duration-300',
            isMenuOpen ? '-rotate-45 top-3' : 'top-5',
          ]"></span>
        </div>
      </button>
    </div>

    <nav :class="[
      'z-40 transition-all duration-300 gap-4',
      isMenuOpen
        ? 'absolute top-full left-0 w-full flex flex-col gap-6 items-center bg-[#111827] p-6 md:flex md:flex-row md:justify-between md:bg-transparent md:p-0'
        : 'hidden md:flex md:flex-row md:justify-between md:bg-transparent md:p-0'
    ]">
      <ul class="flex flex-col items-center space-y-5 md:flex-row md:space-x-5 md:space-y-0">
        <li v-for="item in Menu" :key="item.name" class="group relative">
          <a :href="item.href" @click="scrollToSection(item.href)"
            class="relative block text-blue-100 hover:text-blue-400 transition-all duration-300 text-xl md:text-base font-medium group">
            {{ item.name }}
            <span
              class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-400 transition-all duration-300 group-hover:w-full"></span>
          </a>
        </li>
      </ul>

      <div class="mt-4 md:mt-0">
        <button
          class="px-6 py-2.5 bg-gradient-to-r from-blue-500 to-cyan-500 text-white rounded-full hover:shadow-lg hover:shadow-blue-500/25 transition-all duration-300 hover:scale-105"
          @click="openLinkedIn">
          تواصل الآن
        </button>
      </div>
    </nav>

  </header>
</template>

<script setup>
import { ref } from "vue";

const Menu = ref([
  { name: "من أنا", href: "#about" },
  { name: "الشهادات", href: "#certificates" },
  { name: "المهارات", href: "#skills" },
  { name: "المشاريع", href: "#projects" },
  { name: "تواصل معي", href: "#contact" },
]);

const isMenuOpen = ref(false);

const scrollToSection = (href) => {
  isMenuOpen.value = false;
  const section = document.querySelector(href);
  if (section) {
    section.scrollIntoView({ behavior: "smooth" });
  }
};

const openLinkedIn = () => {
  window.open("https://www.linkedin.com/in/mohamed-hanish-2595b6151", "_blank");
};
</script>
