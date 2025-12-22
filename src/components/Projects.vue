<template>
  <section
    id="projects"
    class="overflow-hidden w-full min-h-screen flex flex-col items-center justify-center px-6 md:px-20 py-16 gap-12"
  >
    <!-- عنوان مشاريع Desktop -->
    <h2
      class="text-4xl md:text-5xl font-extrabold text-blue-500 mb-12 font-sans"
    >
      مشاريع Desktop
    </h2>

    <div data-aos="fade-left" data-aos-delay="100"
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8 w-full max-w-6xl"
    >
      <div
        v-for="project in desktopProjects"
        :key="project.name"
        class="bg-white rounded-2xl shadow-lg shadow-blue-500 overflow-hidden transition-all duration-300 hover:scale-105"
      >
        <!-- Carousel صور المشروع -->
        <div class="flex overflow-x-auto gap-2 p-4">
          <img
            v-for="img in project.images"
            :key="img"
            :src="img"
            alt="Project image"
            class="w-60 h-40 object-cover rounded-xl flex-shrink-0"
          />
        </div>

        <!-- اسم المشروع + زر التفاصيل -->
        <div class="p-5 flex flex-col gap-3">
          <h3 class="text-xl font-bold text-blue-600 font-sans">
            {{ project.name }}
          </h3>
          <button
            @click="project.showDetails = !project.showDetails"
            class="mt-2 px-4 py-2 bg-gradient-to-r from-blue-500 to-cyan-500 text-white rounded-full hover:shadow-lg hover:shadow-blue-500/25 transition-all duration-300"
          >
            {{ project.showDetails ? "إخفاء التفاصيل" : "عرض التفاصيل" }}
          </button>

          <!-- تفاصيل المشروع تظهر عند الضغط -->
          <p
            v-if="project.showDetails"
            class="text-gray-700 text-sm md:text-base mt-2"
          >
            {{ project.details }}
          </p>
        </div>
      </div>
    </div>

    <!-- عنوان مشاريع Web -->
    <h2
      class="text-4xl md:text-5xl font-extrabold text-blue-500 mb-12 mt-20 font-sans"
    >
      مشاريع Web
    </h2>

    <div data-aos="fade-right" data-aos-delay="100"
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8 w-full max-w-6xl"
    >
      <div
        v-for="project in webProjects"
        :key="project.name"
        class="bg-white rounded-2xl shadow-lg shadow-blue-500 overflow-hidden transition-all duration-300 hover:scale-105"
      >
        <!-- Carousel صور المشروع -->
        <div class="flex overflow-x-auto gap-2 p-4">
          <img
            v-for="img in project.images"
            :key="img"
            :src="img"
            alt="Project image"
            class="w-60 h-40 object-cover rounded-xl flex-shrink-0"
          />
        </div>

        <!-- اسم المشروع + زر التفاصيل -->
        <div class="p-5 flex flex-col gap-3">
          <h3 class="text-xl font-bold text-blue-600 font-sans">
            {{ project.name }}
          </h3>
          <button
            @click="project.showDetails = !project.showDetails"
            class="mt-2 px-4 py-2 bg-gradient-to-r from-blue-500 to-cyan-500 text-white rounded-full hover:shadow-lg hover:shadow-blue-500/25 transition-all duration-300"
          >
            {{ project.showDetails ? "إخفاء التفاصيل" : "عرض التفاصيل" }}
          </button>

          <!-- تفاصيل المشروع تظهر عند الضغط -->
          <p
            v-if="project.showDetails"
            class="text-gray-700 text-sm md:text-base mt-2"
          >
            {{ project.details }}
          </p>

          <!-- أزرار الكود والLive تظهر فقط إذا موجودة -->
          <div
            v-if="project.codeUrl || project.liveProject"
            class="flex gap-3 mt-3"
          >
            <a
              v-if="project.codeUrl"
              :href="project.codeUrl"
              target="_blank"
              class="px-4 py-2 bg-gray-800 text-white rounded-full hover:bg-gray-900 transition-all duration-300 text-sm"
            >
              الكود
            </a>
            <a
              v-if="project.liveProject"
              :href="project.liveProject"
              target="_blank"
              class="px-4 py-2 bg-blue-500 text-white rounded-full hover:bg-blue-600 transition-all duration-300 text-sm"
            >
              العرض
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { reactive } from "vue";

// مشاريع Desktop
const desktopProjects = reactive([
  {
    name: "نظام قطع الغيار المكامل",
    images: [
      new URL("../assets/projects/project1/img1.png", import.meta.url).href,
      new URL("../assets/projects/project1/img2.png", import.meta.url).href,
      new URL("../assets/projects/project1/img3.png", import.meta.url).href,
    ],
    details:
      "نظام متكامل لإدارة مبيعات قطع الغيار، المخزون، والفواتير بطريقة احترافية مع تقارير لحظية ونسخ احتياطي تلقائي، مما يضمن كفاءة العمل واستمراريته.",
    showDetails: false,
  },
  {
    name: "نظام أرشفة المستندات",
    images: [
      new URL("../assets/projects/project2/img1.png", import.meta.url).href,
      new URL("../assets/projects/project2/img2.png", import.meta.url).href,
      new URL("../assets/projects/project2/img3.png", import.meta.url).href,
    ],
    details:
      "تطبيق لإدارة الأرشيف الرقمي للمستندات مع تصنيف وتنظيم سريع، وحماية البيانات لضمان سهولة الوصول ومرونة العمل داخل المؤسسة.",
    showDetails: false,
  },
]);

// مشاريع Web
const webProjects = reactive([
  {
    name: "Dashboard Vue-js",
    images: [
      new URL("../assets/projects/project8/img1.png", import.meta.url).href,
      new URL("../assets/projects/project8/img2.png", import.meta.url).href,
      new URL("../assets/projects/project8/img3.png", import.meta.url).href,
    ],
    details: "html,css,Tailwind,vue.js",
    showDetails: false,
    codeUrl: "https://github.com/mohamedhanish/Dashboard-Vue-js",
    liveProject: "https://mohamedhanish.github.io/Dashboard-Vue-js/",
  },
  {
    name: "Minimal Agency Web Template",
    images: [
      new URL("../assets/projects/project3/img1.png", import.meta.url).href,
      new URL("../assets/projects/project3/img2.png", import.meta.url).href,
      new URL("../assets/projects/project3/img3.png", import.meta.url).href,
    ],
    details: "Template لصفحة وكالة بسيطة وحديثة باستخدام HTML وCSS.",
    showDetails: false,
    codeUrl: "https://github.com/mohamedhanish/HTML_AND_CSS_Template_One",
    liveProject: "https://mohamedhanish.github.io/HTML_AND_CSS_Template_One/",
  },
  {
    name: "Dashboard قالب لوحة تحكم طعام",
    images: [
      new URL("../assets/projects/project4/img1.png", import.meta.url).href,
    ],
    details: "Dashboard لإدارة مطعم مع HTML وCSS.",
    showDetails: false,
    codeUrl:
      "https://github.com/mohamedhanish/mohamedhanish-Food_Dashboard_HTML_AND_CSS_Arabic_Template",
    liveProject:
      "https://mohamedhanish.github.io/mohamedhanish-Food_Dashboard_HTML_AND_CSS_Arabic_Template/",
  },
  {
    name: "LandingPage",
    images: [
      new URL("../assets/projects/project5/img1.png", import.meta.url).href,
      new URL("../assets/projects/project5/img2.png", import.meta.url).href,
      new URL("../assets/projects/project5/img3.png", import.meta.url).href,
    ],
    details: "LandingPage حديثة باستخدام HTML وTailwind CSS.",
    showDetails: false,
    codeUrl: "https://github.com/mohamedhanish/TailwindTemplate-LandingPage",
    liveProject:
      "https://mohamedhanish.github.io/TailwindTemplate-LandingPage/",
  },
  {
    name: "CRDUS تطبيق مهام بسيط",
    images: [
      new URL("../assets/projects/project6/img1.png", import.meta.url).href,
      new URL("../assets/projects/project6/img2.png", import.meta.url).href,
    ],
    details: "تطبيق CRUD بسيط باستخدام HTML وCSS وJS لإدارة المهام.",
    showDetails: false,
    codeUrl: "https://github.com/mohamedhanish/Simple_CRUD_HTML_CSS_JS",
    liveProject: "https://mohamedhanish.github.io/Simple_CRUD_HTML_CSS_JS/",
  },
]);
</script>
