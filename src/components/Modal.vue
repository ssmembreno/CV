<script setup>
import { computed } from 'vue';

const props = defineProps({
  isOpen: Boolean,
  project: Object
});

const emit = defineEmits(['close']);

const closeModal = () => {
  emit('close');
};

// Prevent scrolling on body when modal is open
if (typeof window !== 'undefined') {
  const body = document.body;
  if (props.isOpen) {
    body.style.overflow = 'hidden';
  } else {
    body.style.overflow = 'auto';
  }
}
</script>

<template>
  <Transition name="fade">
    <div v-if="isOpen" class="fixed inset-0 z-50 overflow-y-auto" aria-labelledby="modal-title" role="dialog" aria-modal="true">
      <!-- Backdrop -->
      <div class="fixed inset-0 bg-black/80 transition-opacity" @click="closeModal"></div>

      <div class="flex min-h-full items-center justify-center p-4 text-center sm:p-0">
        <Transition name="scale">
          <div v-if="isOpen" class="relative transform overflow-hidden rounded-lg bg-[#1a1d3a] text-left shadow-xl transition-all sm:my-8 sm:w-full sm:max-w-4xl border border-gray-700">
            
            <!-- Close button -->
            <button @click="closeModal" class="absolute top-4 right-4 text-gray-400 hover:text-white z-10">
              <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
              </svg>
            </button>

            <div class="flex flex-col md:flex-row">
              <!-- Image Section -->
              <div class="md:w-1/2 relative bg-gray-900">
                <img 
                  v-if="project?.image" 
                  :src="project.image" 
                  :alt="project.title" 
                  class="w-full h-64 md:h-full object-cover"
                >
                <div class="absolute inset-0 bg-gradient-to-t from-[#1a1d3a] to-transparent md:bg-gradient-to-r"></div>
              </div>

              <!-- Content Section -->
              <div class="md:w-1/2 p-8">
                <div class="mb-6">
                  <h3 v-if="project?.subtitle" class="text-sm uppercase text-cyan-400 mb-2 font-bold tracking-wider">
                    {{ project.subtitle }}
                  </h3>
                  <h2 class="text-3xl font-bold text-white mb-4 leading-tight">
                    {{ project?.title }}
                  </h2>
                  <p class="text-gray-300 leading-relaxed text-lg">
                    {{ project?.description }}
                  </p>
                </div>

                <!-- Technologies -->
                <div class="mb-8">
                  <h4 class="text-white font-semibold mb-3 border-b border-gray-700 pb-2">Tecnologías</h4>
                  <div class="flex flex-wrap gap-2">
                    <span 
                      v-for="(tech, index) in project?.technologies" 
                      :key="index"
                      class="px-3 py-1 text-xs font-bold rounded-full text-white shadow-sm"
                      :class="tech.color"
                    >
                      {{ tech.name }}
                    </span>
                  </div>
                </div>

                <!-- Links -->
                <div class="flex gap-4 mt-auto">
                  <a 
                    v-if="project?.links?.github" 
                    :href="project.links.github" 
                    target="_blank" 
                    rel="noopener noreferrer"
                    class="flex items-center gap-2 px-6 py-3 bg-gray-700 hover:bg-gray-600 text-white rounded-lg transition-colors font-medium"
                  >
                    <i class="fab fa-github"></i>
                    <span>Código</span>
                  </a>
                  <a 
                    v-if="project?.links?.live" 
                    :href="(!project.LinkDisabled) ? project.links.live : undefined" 
                    :target="(!project.LinkDisabled) ? '_blank' : undefined" 
                    rel="noopener noreferrer"
                    class="flex items-center gap-2 px-6 py-3 rounded-lg transition-colors font-medium"
                    :class="[
                      project.LinkDisabled 
                        ? 'bg-gray-600 text-gray-400 cursor-not-allowed opacity-70' 
                        : 'bg-cyan-600 hover:bg-cyan-500 text-white shadow-lg shadow-cyan-900/20'
                    ]"
                    @click="(e) => project.LinkDisabled && e.preventDefault()"
                  >
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
                    </svg>
                    <span>Ver Sitio</span>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </Transition>
      </div>
    </div>
  </Transition>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.scale-enter-active,
.scale-leave-active {
  transition: all 0.3s ease;
}

.scale-enter-from,
.scale-leave-to {
  opacity: 0;
  transform: scale(0.95);
}
</style>