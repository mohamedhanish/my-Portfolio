<template>
  <section
    id="certificates"
    class="overflow-hidden w-full min-h-screen flex flex-col items-center justify-center
           px-6 md:px-20 py-16 gap-10"
  >
    <h2 class="text-4xl md:text-5xl font-extrabold text-blue-500 mb-8 font-sans">
      الشهادات
    </h2>

    <div
      data-aos="fade-up"
      data-aos-delay="100"
      class="grid grid-cols-1 sm:grid-cols-2 gap-8 w-full max-w-5xl"
    >
      <div
        v-for="cert in certificates"
        :key="cert.title"
        class="flex flex-col bg-white rounded-2xl
               shadow-[0_10px_25px_rgba(0,0,0,0.15)]
               transition-all duration-300 hover:scale-[1.02]"
      >
        <div class="w-full aspect-[4/3] bg-gray-100 rounded-t-2xl flex items-center justify-center">
          <img
            :src="cert.image"
            :alt="cert.title"
            class="max-w-full max-h-full object-contain"
          />
        </div>

        <div class="p-6 flex flex-col gap-4 items-center w-full">
          <h3 class="text-base md:text-lg font-bold text-gray-800 font-sans text-center">
            {{ cert.title }}
          </h3>

          <div class="flex flex-col sm:flex-row gap-3 w-full">
            <a
              :href="cert.pdf"
              target="_blank"
              class="flex-1 text-center px-5 py-3 rounded-xl
                     bg-gradient-to-r from-blue-400 to-blue-600
                     text-white font-medium font-sans
                     shadow-[0_4px_15px_rgba(59,130,246,0.5)]
                     transition-all duration-300 hover:opacity-90"
            >
              عرض PDF
            </a>

            <button
              @click="openImage(cert.image)"
              class="flex-1 px-5 py-3 rounded-xl
                     border border-blue-500 text-blue-500
                     font-medium font-sans
                     transition-all duration-300 hover:bg-blue-50"
            >
              عرض الصورة
            </button>
          </div>
        </div>
      </div>
    </div>

    <div
      v-if="selectedImage"
      class="fixed inset-0 z-50 bg-black/80 flex items-center justify-center px-4"
      @click.self="closeImage"
    >
      <div class="relative max-w-5xl w-full">
<button
  @click="closeImage"
  class="absolute top-4 right-4 text-white text-3xl font-bold
         bg-black/40 rounded-full w-10 h-10
         flex items-center justify-center
         hover:bg-black/60 transition"
>
  ✕
</button>


        <img
          :src="selectedImage"
          class="w-full max-h-[90vh] object-contain rounded-xl"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const selectedImage = ref(null);

const openImage = (img) => {
  selectedImage.value = img;
};

const closeImage = () => {
  selectedImage.value = null;
};

const certificates = [
  {
    title:
      "دبلوم عالي - تخصص برمجة المعهد العالي للتقنية الصناعية - النجيلة | [2025]",
    image: new URL(
      "../assets/Certificates/Certificate1.jpg",
      import.meta.url
    ).href,
    pdf: new URL(
      "../assets/Certificates/Certificate1.pdf",
      import.meta.url
    ).href,
  },
  {
    title: "دبلوم مهني في برمجة المنظومات [2024]",
    image: new URL(
      "../assets/Certificates/Certificate2.jpg",
      import.meta.url
    ).href,
    pdf: new URL(
      "../assets/Certificates/Certificate2.pdf",
      import.meta.url
    ).href,
  },
];
</script>
