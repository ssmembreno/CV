<template>
  <div class="min-h-screen bg-[#0f1126] text-white font-sans px-2 py-2">
    <section
      class="rounded-xl px-4 sm:px-6 pt-4 mt-4"
      :style="heroBackground"
    >
      <!-- Navbar -->
      <nav class="px-4 sm:px-6 py-3 flex items-center justify-center text-sm sm:text-base md:text-lg">
        <div class="nav-bar flex gap-6 sm:gap-8 flex-wrap justify-center">
          <a href="#" class="text-white hover:text-purple-400 text-xl">Inicio</a>
          <a href="#" class="text-white hover:text-purple-400 text-xl">Sobre mí</a>
          <a href="#" class="text-white hover:text-purple-400 text-xl">Proyectos</a>
          <a href="#" class="text-white hover:text-purple-400 text-xl">Contacto</a>
        </div>
      </nav>

      <!-- Hero -->
      <div class="flex flex-col lg:flex-row items-center justify-between">
        <!-- Texto -->
        <div class="max-w-xl w-full px-4 sm:px-6 lg:px-0 mt-10 lg:mt-0 lg:ml-16 text-center lg:text-left">
          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-josefin font-bold mb-6">Hola, Soy Samuel</h1>
          <h2 class="text-2xl sm:text-3xl lg:text-4xl font-semibold mb-8 bg-gradient-to-r from-[#0CFFFF] via-[#dc0025] to-[#100425] bg-clip-text text-transparent">
            Full-stack developer
          </h2>
          <p class="text-base sm:text-lg lg:text-xl text-gray-300 mb-5 leading-relaxed">
            Soy un desarrollador web con formación en un grado superior<br />
            de desarrollo de aplicaciones web (DAW).<br /><br />
            Me enfoco en escribir código limpio, mantenible y orientado al<br />
            usuario, creando interfaces modernas y manteniendo aplicaciones.
          </p>
          <div class="flex flex-col lg:flex-row items-center">
            <div class="grid sm:grid-cols-3 gap-4">
              <button class="border-2 border-solid text-white font-bold px-6 py-2 rounded-full shadow hover:opacity-80 transition duration-300">Github</button>
              <button class="border-2 border-solid text-white font-bold px-6 py-2 rounded-full shadow hover:opacity-80 transition duration-300">LinkedIn</button>
              <button class="border-2 border-solid text-white font-bold px-6 py-2 rounded-full shadow hover:opacity-80 transition duration-300">Infojobs</button>
              <button class="border-2 border-solid text-white font-bold px-6 py-2 rounded-full shadow hover:opacity-80 transition duration-300">CV</button>
            </div>
          </div>
        </div>

        <!-- Imagen con iconos posicionados responsivamente -->
        <div class="relative w-[240px] sm:w-[280px] md:w-[320px] lg:w-[380px] mx-auto mb-10 lg:mr-10">
          <!-- JS Icon -->
          <img
            src="/public/img/icons/js.png"
            alt="JavaScript"
            class="floating absolute z-20
              top-[200px] left-[15px]
              sm:top-[230px] sm:left-[25px]
              md:top-[260px] md:left-[30px]
              lg:top-[340px] lg:left-[40px]
              w-8 h-8 sm:w-9 sm:h-9 md:w-10 md:h-10"
          />

          <!-- Imagen principal -->
          <img
            src="/public/img/samuel.png"
            alt="Samuel"
            class="w-full h-auto object-contain relative z-10 mb-30"
          />

            <!-- CSS Icon -->
            <img
            src="/public/img/icons/css-3.png"
            alt="CSS"
            class="floating absolute z-20
                bottom-[100px]
                right-[5px] sm:right-[25px] md:right-[30px] lg:right-[10px]
                w-8 h-8 sm:w-9 sm:h-9 md:w-10 md:h-10"
            />
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
const heroBackground = `
  background-image: linear-gradient(
    to top,
    rgba(15, 17, 38, 0.1) 0%,
    rgba(220, 0, 37, 0.2) 35%,
    rgba(86, 226, 210, 0.3) 80%,
    rgba(31, 27, 84, 0.3) 100%
  );
`;
</script>