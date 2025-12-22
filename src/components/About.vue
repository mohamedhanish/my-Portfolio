<template>
  <section id="about"
    class=" overflow-hidden pt-24 w-full min-h-screen flex flex-col md:flex-row items-center justify-center px-6 md:px-20 py-16 gap-10">

    <!-- النص -->
    <div data-aos="fade-right" data-aos-delay="500" class="flex-1 flex flex-col justify-center items-start gap-6">
      <h2 class="text-4xl md:text-5xl font-extrabold text-blue-500 font-sans">
        مرحباً، أنا محمد مسعود
      </h2>
      <p class="text-lg md:text-xl text-gray-300 leading-relaxed font-sans">
        مرحبًا، أنا <span class="font-semibold text-white">محمد مسعود</span> —
        مبرمج شغوف أبحث دائمًا عن فرص لتعلّم التقنيات الجديدة وبناء مشاريع حقيقية.
        أعمل على تحويل الأفكار إلى تطبيقات مفيدة، وأسعى لتحسين مهاراتي خطوة بخطوة مع كل مشروع أقدّمه.
      </p>

      <button
        class="px-6 py-2.5 bg-gradient-to-r from-blue-500 to-cyan-500 text-white rounded-full hover:shadow-lg hover:shadow-blue-500/25 transition-all duration-300 hover:scale-105"
        @click="openLinkedIn">
        تواصل الآن
      </button>


    </div>

    <!-- الصورة -->
    <div data-aos="fade-left" data-aos-delay="500"
  class="flex-1 flex justify-center items-center rounded-full shadow-lg shadow-blue-500">
      <img src="../assets/portfolio/portfolio-app.jpg" alt="محمد مسعود"
        class="rounded-full shadow-lg w-80 md:w-full object-cover">
    </div>

  </section>
</template>

<script setup>
// لا يوجد كود JS لهذا القسم حاليا
const openLinkedIn = () => {
  window.open('https://www.linkedin.com/in/mohamed-hanish-2595b6151', '_blank');
};
</script>
