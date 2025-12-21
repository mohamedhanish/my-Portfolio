<template>
  <section  id="skills" class="w-full min-h-screen flex flex-col items-center justify-center px-6 md:px-20 py-16 gap-10">
    
    <!-- عنوان القسم -->
    <h2 class="text-4xl md:text-5xl font-extrabold text-blue-500 mb-8 font-sans">
      المهارات
    </h2>

    <!-- قائمة المهارات -->
    <div 
   class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-6 w-full max-w-6xl">
      <div 
        v-for="skill in skills" 
        :key="skill.name" 
        class="flex flex-col items-center justify-center p-6 rounded-2xl cursor-pointer 
               bg-gradient-to-br from-blue-400 to-blue-600 
               shadow-[0_4px_15px_rgba(59,130,246,0.5)]
               transition-all duration-300 hover:scale-105">
        <img :src="skill.icon" :alt="skill.name" class="w-16 h-16 mb-4 object-contain"/>
        <span class="text-lg font-medium text-white font-sans">{{ skill.name }}</span>
      </div>
    </div>

  </section>
</template>

<script setup>
const skills = [
  { name: "HTML5", icon: new URL('../assets/skills/html.svg', import.meta.url).href },
  { name: "CSS3", icon: new URL('../assets/skills/css.svg', import.meta.url).href },
  { name: "JavaScript", icon: new URL('../assets/skills/js.svg', import.meta.url).href },
  { name: "Vue.js", icon: new URL('../assets/skills/vue.svg', import.meta.url).href },
  { name: "Tailwind CSS", icon: new URL('../assets/skills/tailwind.svg', import.meta.url).href },
  { name: "C#", icon: new URL('../assets/skills/csharp.svg', import.meta.url).href },
  { name: "SQL", icon: new URL('../assets/skills/sql.svg', import.meta.url).href },
  { name: "Git", icon: new URL('../assets/skills/github.svg', import.meta.url).href },
];
</script>


