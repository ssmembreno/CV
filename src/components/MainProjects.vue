<template>
  <section
    ref="projectsSection"
    class="relative bg-[#0f1126] py-16 px-6 md:px-20 text-white overflow-hidden"
  >
    <!-- Línea vertical -->
    <div class="hidden md:block absolute left-12 top-20 h-full border-l-4 border-cyan-500 z-0"></div>

    <!-- Tren animado -->
    <div
      class="hidden md:block absolute left-8 w-12 h-20 overflow-hidden"
      :style="{ transform: `translateY(${trainPosition}px)` }"
    >
      <img
        src="/public/img/train.png"
        alt="Tren"
        class="w-full h-full object-cover relative z-10"
      />
      <div class="absolute inset-0 z-20 pointer-events-none"
        style="background: linear-gradient(
          180deg,
          rgba(15, 17, 38, 0.1) 0%,
          rgba(220, 0, 37, 0.2) 35%,
          rgba(86, 226, 210, 0.3) 80%,
          rgba(31, 27, 84, 0.3) 100%
        );">
      </div>
    </div>

    <div class="max-w-6xl mx-auto relative z-10">
          <h2 class="text-5xl sm:text-6xl lg:text-6xl font-semibold mb-8 bg-gradient-to-r from-[#0CFFFF] via-[#ff0000] to-[#ff0000] bg-clip-text text-transparent">
            Proyectos
          </h2>
      <p class="text-lg text-gray-300 mb-12">
        Estos son algunos de los proyectos que he desarollado.
      </p>

      <div class="grid md:grid-cols-1 gap-15">
        <!-- Proyecto 1 -->
        <article class="flex flex-col md:flex-row items-center bg-gradient-to-br from-gray-900 to-gray-800 rounded-lg overflow-hidden shadow-lg">
          <img src="/public/img/image.png" alt="Project screenshot" class="object-cover rounded-lg md:w-1/2 sm:ml-4 ">
          <div class="p-6 flex flex-col justify-between">
            <div>
              <h3 class="text-sm uppercase text-blue-400 mb-2">Proyecto destacado</h3>
              <h2 class="text-xl font-semibold mb-4">Galeria de arte Enmanuel Membreño</h2>
              <p class="text-gray-300 mb-2">
               He diseñado y desarrollado una plataforma en línea para una galería de arte que exhibe las obras de un artista pintor hondureño,
                con la finalidad de ofrecer a los usuarios una experiencia única de visualización y exploración de arte. 
               El sitio permite a los visitantes descubrir, interactuar y valorar las obras de manera sencilla e intuitiva.
              </p>
              <!-- Tecnologías -->
              <div class="flex flex-wrap gap-1 mt-4">
                <span class="px-3 py-1 text-sm bg-pink-700 text-white rounded-full font-bold">HTML</span>
                <span class="px-3 py-1 text-sm bg-cyan-700 text-white rounded-full font-bold">CSS</span>
                <span class="px-3 py-1 text-sm bg-yellow-500 text-white rounded-full font-bold">JavaScript</span>
                <span class="px-3 py-1 text-sm bg-cyan-900 text-white rounded-full font-bold">Boostrap</span>
                <span class="px-3 py-1 text-sm bg-blue-400 text-white rounded-full font-bold">PHP</span>
                <span class="px-3 py-1 text-sm bg-red-700 text-white rounded-full font-bold">Laravel</span>
                <span class="px-3 py-1 text-sm bg-purple-700 text-white rounded-full font-bold">MySQL</span>
              </div>
            </div>
            <div class="flex space-x-4 mt-4">
              <a href="https://github.com/ssmembreno/GaleriaArteEnmanuel" target="_blank" aria-label="GitHub" class="text-gray-400 hover:text-white"><i class="fab fa-github"></i></a>
            </div>
          </div>
        </article>

        <!-- Proyecto 2 -->
        <article class="flex flex-col md:flex-row-reverse items-start bg-gradient-to-br from-gray-900 to-gray-800 rounded-lg overflow-hidden shadow-lg">
          <img src="/public/img/LsFitness.png" alt="LS Fitness image" class="object-cover rounded-lg md:w-1/2 sm:ml-4 mt-5 mb-5 mr-5">
          <div class="p-6 flex flex-col justify-between">
            <div>
              <h2 class="text-xl font-semibold mb-4">LS Fitness</h2>
              <p class="text-gray-300 mb-4">
               LS Fitness, me encargué de actualizar y mejorar diversas secciones del sitio web para optimizar su funcionalidad y estética.
                El objetivo principal fue mejorar la experiencia del usuario, asegurando una navegación fluida.
              </p>
              <!-- Tecnologías -->
              <div class="flex flex-wrap gap-2 mt-4">
                <span class="px-3 py-1 text-sm bg-yellow-700 text-white rounded-full">WordPress</span>
              </div>
            </div>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const trainPosition = ref(0);
const projectsSection = ref(null);

const updateTrainPosition = () => {
  if (!projectsSection.value) return;

  const section = projectsSection.value;
  const sectionTop = section.getBoundingClientRect().top;
  const sectionHeight = section.offsetHeight;
  const windowHeight = window.innerHeight;

  const startTrigger = windowHeight * 0.7;
  const endTrigger = -sectionHeight + windowHeight * 0.823;

  let percentage = 0;

  if (sectionTop < startTrigger && sectionTop > endTrigger) {
    const totalScrollable = startTrigger - endTrigger;
    const scrolled = startTrigger - sectionTop;
    percentage = scrolled / totalScrollable;
  } else if (sectionTop <= endTrigger) {
    percentage = 1;
  } else {
    percentage = 0;
  }

  const maxTrainTravel = sectionHeight - 10;
  trainPosition.value = percentage * maxTrainTravel;
};

onMounted(() => {
  updateTrainPosition();
  window.addEventListener('scroll', updateTrainPosition);
});

onUnmounted(() => {
  window.removeEventListener('scroll', updateTrainPosition);
});
</script>
