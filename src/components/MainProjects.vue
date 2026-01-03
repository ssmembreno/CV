<script setup>
import { ref, onMounted, onUnmounted, nextTick } from 'vue';
import VanillaTilt from 'vanilla-tilt';
import Modal from './Modal.vue';

const trainPosition = ref(0);
const projectsSection = ref(null);
const isModalOpen = ref(false);
const selectedProject = ref(null);

const projects = [
  {
    id: 1,
    title: "Galeria de arte Enmanuel Membreño",
    subtitle: "Proyecto destacado",
    description: "La Galeria de arte Enmanuel Membreño es una plataforma web que permite a los usuarios visualizar visualizar obras de arte de el artista. El proyecto lo he desarrollado completamente con Laravel, PHP, HTML, CSS y JavaScript. Utilizando la base de datos MySQL para almacenar diferentes datos de la plataforma, se aplico correctamente el uso de MVC, La aplicación cuenta con un sistema de autenticación, y un sistema de roles y permisos. Todo el proyecto se gestiono utilizando git y github.",
    image: "/public/img/image.png",
    links: {
      github: "https://github.com/ssmembreno/GaleriaArteEnmanuel",
      live: "https://www.galeriaenmanuel.com/"
    },
    LinkDisabled: true,
    technologies: [
      { name: "HTML", color: "bg-pink-700" },
      { name: "CSS", color: "bg-cyan-700" },
      { name: "JavaScript", color: "bg-yellow-500" },
      { name: "Boostrap", color: "bg-cyan-900" },
      { name: "PHP", color: "bg-blue-400" },
      { name: "Laravel", color: "bg-red-700" },
      { name: "MySQL", color: "bg-purple-700" },
    ]
  },
  {
    id: 2,
    title: "Infinity Broker | Correduria De Seguros",
    subtitle: "Proyecto destacado",
    description: "Infinity Broker es una plataforma de gestión de seguros en la trabaje como desarrollador fullstack dandole mantenimiento y actualizaciones de nuevas funcionalidades con Laravel 10 y MySQL bajo arquitectura MVC. Implementé nuevas funcionalidades y optimicé el rendimiento del sistema siguiendo metodologías Scrum y flujos de CI/CD. En el frontend, construí componentes modulares con Blade, Vite y Bootstrap 5 aplicando el estándar BEM para garantizar escalabilidad y mantenibilidad del código. Manteniendo un flujo de trabajo organizado y eficiente, utilizando Git y GitHub para control de versiones y colaboración con el equipo.",
    image: "/public/img/Infinity.png",
    links: {
      live: "https://infinitybrokershn.com/"
    },
    LinkDisabled: false,
    technologies: [
      { name: "HTML", color: "bg-pink-700" },
      { name: "CSS", color: "bg-cyan-700" },
      { name: "JavaScript", color: "bg-yellow-500" },
      { name: "Boostrap", color: "bg-cyan-900" },
      { name: "PHP", color: "bg-blue-400" },
      { name: "Laravel", color: "bg-red-700" },
      { name: "MySQL", color: "bg-purple-700" },
      { name: "Blade", color: "bg-orange-500" },
    ]
  },
  {
    id: 3,
    title: "LS Fitness",
    subtitle: "",
    description: "LS Fitness, me encargué de actualizar y mejorar diversas secciones del sitio web para optimizar su funcionalidad y estética. El objetivo principal fue mejorar la experiencia del usuario.",
    image: "/public/img/LsFitness.png",
    links: {
      live: "https://leridasturm.com/"
    },
    LinkDisabled: false,
    technologies: [
      { name: "WordPress", color: "bg-yellow-700" },
    ]
  },
  {
    id: 4,
    title: "Fiscape",
    subtitleClass: "text-red-600",
    subtitle: "Proyecto en DESARROLLO",
    description: "Fiscape es un proyecto en desarrollo en la que se busca un mejor manejo de finanzas personales. En la aplicación se busca que el usuario pueda registrar sus gastos y ingresos, y que pueda ver un resumen de sus finanzas. En ella podras ver tus gastos y ingresos en un gráfico, y podrás ver tus finanzas en un resumen, exportar tus finanzas a un archivo CSV y PDF.",
    image: "/public/img/fiscape.png",
    links: {
       github: "https://github.com/ssmembreno/Fiscape",
       live: "https://fiscape.com/"
    },
    LinkDisabled: true,
    technologies: [
      { name: "HTML", color: "bg-pink-700" },
      { name: "CSS", color: "bg-cyan-700" },
      { name: "JavaScript", color: "bg-yellow-500" },
      { name: "PHP", color: "bg-blue-400" },
      { name: "Laravel", color: "bg-red-700" },
      { name: "Vue 3", color: "bg-green-500" },
      { name: "Inertia.js", color: "bg-blue-400" },
      { name: "MySQL", color: "bg-purple-700" },
      { name: "Boostrap", color: "bg-cyan-900" },
      { name: "Blade", color: "bg-orange-500" },
      { name: "tailwind", color: "bg-yellow-500" },
    ]
  }
];

const openProjectModal = (project) => {
  selectedProject.value = project;
  isModalOpen.value = true;
};

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

onMounted(async () => {
  updateTrainPosition();
  window.addEventListener('scroll', updateTrainPosition);

  // Espera a que todo el DOM del componente esté montado
  await nextTick();

  // Selecciona todos los elementos .card-3d y aplica VanillaTilt
  const cards = document.querySelectorAll(".card-3d");
  if (cards.length) {
    VanillaTilt.init(cards, {
      max: 5,
      speed: 700,
      glare: true,
      "max-glare": 0.2,
      perspective: 1000
    });
  }
});

onUnmounted(() => {
  window.removeEventListener('scroll', updateTrainPosition);
});
</script>

<template>
  <section
    ref="projectsSection"
    class="relative bg-[#0f1126] py-16 px-6 md:px-20 text-white overflow-hidden"
  >
  <a id="proyects"></a>
    <!-- Línea vertical -->
    <div class="hidden md:block absolute left-13 top-20 h-full border-l-4 border-cyan-500 z-0"></div>

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
          
      <div class="grid md:grid-cols-1 gap-15">
        
        <article
          v-for="(project, index) in projects"
          :key="project.id"
          @click="openProjectModal(project)"
          class="card-3d cursor-pointer transform transition-transform duration-300 ease-out hover:-translate-y-2 flex flex-col items-center bg-gradient-to-br from-gray-900 to-gray-800 rounded-lg overflow-hidden shadow-lg"
          :class="index % 2 === 0 ? 'md:flex-row' : 'md:flex-row-reverse'"
        >
          <img 
            :src="project.image" 
            :alt="project.title" 
            class="card-3d object-cover rounded-lg md:w-1/2 sm:ml-4"
            :class="index % 2 === 0 ? '' : 'mt-10 mb-5 mr-5'"
          >
          <div class="p-6 flex flex-col justify-between w-full md:w-1/2">
            <div>
              <h3 
                v-if="project.subtitle" 
                class="text-sm uppercase mb-2" 
                :class="project.subtitleClass || 'text-blue-400'"
              >
                {{ project.subtitle }}
              </h3>
              <h2 class="text-xl font-semibold mb-4">{{ project.title }}</h2>
              <p class="text-gray-300 mb-2">
                {{ project.description }}
              </p>
              <!-- Tecnologías -->
              <div class="flex flex-wrap gap-1 mt-4">
                <span 
                  v-for="tech in project.technologies" 
                  :key="tech.name"
                  class="px-3 py-1 text-sm text-white rounded-full font-bold"
                  :class="tech.color"
                >
                  {{ tech.name }}
                </span>
              </div>
            </div>
            <div class="flex space-x-4 mt-4">
              <a v-if="project.links.github" :href="project.links.github" target="_blank" aria-label="GitHub" class="mt-1" @click.stop>
                <i class="fab fa-github"></i>
              </a>
              <a 
                v-if="project.links.live" 
                :href="(!project.LinkDisabled) ? project.links.live : undefined" 
                :target="(!project.LinkDisabled) ? '_blank' : undefined" 
                aria-label="Link" 
                class="mt-2 text-gray-400"
                :class="{ 'hover:text-white': !project.LinkDisabled, 'cursor-not-allowed opacity-50': project.LinkDisabled }"
                @click.stop="(e) => project.LinkDisabled && e.preventDefault()"
              >
                <img src="/public/img/icons/external-link.png" :alt="project.title" width="15">
              </a>
            </div>
          </div>
        </article>

      </div>
    </div>
  </section>

  <Modal 
    :isOpen="isModalOpen" 
    :project="selectedProject" 
    @close="isModalOpen = false" 
  />
</template>


