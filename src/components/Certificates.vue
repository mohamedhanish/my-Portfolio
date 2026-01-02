<template>
  <section
    id="certificates"
    class="w-full min-h-screen flex flex-col items-center justify-center
           px-6 md:px-20 py-16 gap-12"
  >
    <h2 class="text-4xl md:text-5xl font-extrabold text-blue-500 font-sans">
      الشهادات
    </h2>

    <div
      data-aos="fade-up"
      data-aos-delay="100"
      class="w-full max-w-4xl flex flex-col gap-5"
    >
      <div
        v-for="cert in certificates"
        :key="cert.title"
        class="group flex items-center justify-between gap-6
               bg-white rounded-2xl px-6 py-5
               shadow-[0_8px_20px_rgba(0,0,0,0.12)]
               transition-all duration-300 hover:shadow-[0_12px_30px_rgba(0,0,0,0.18)]"
      >
        <!-- الجهة اليسرى -->
        <div class="flex items-center gap-4">
          <span
            class="w-3 h-3 rounded-full bg-blue-500
                   group-hover:scale-125 transition-transform"
          ></span>

          <h3 class="text-base md:text-lg font-semibold text-gray-800 font-sans">
            {{ cert.title }}
          </h3>
        </div>

        <!-- السنة -->
        <span
          class="text-sm font-medium text-blue-500 bg-blue-50
                 px-4 py-1.5 rounded-full font-sans"
        >
          {{ cert.year }}
        </span>
      </div>
    </div>
  </section>
</template>
<script setup>
const certificates = [
  {
    title: "دبلوم مهني في برمجة المنظومات",
    year: 2024,
  },
  {
    title: "دبلوم عالي – تخصص برمجة",
    year: 2025,
  },
];
</script>
