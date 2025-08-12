<template>
  <div class="min-h-screen bg-[#0f1126] text-white font-sans px-2 py-2">
    <section
      class="rounded-xl px-4 sm:px-6 pt-4 mt-4"
      :style="heroBackground"
    >
      <!-- Navbar -->
      <nav class="px-4 sm:px-6 py-3 flex items-center justify-center text-sm sm:text-base md:text-lg">
        <div class="nav-bar flex gap-6 sm:gap-8 flex-wrap justify-center">
          <a href="#" class="text-white hover:text-teal-300 text-xl">Inicio</a>
          <a href="#about" class="text-white  hover:text-teal-300 text-xl">Sobre mí</a>
          <a href="#proyects" class="text-white  hover:text-teal-300 text-xl">Proyectos</a>
          <a href="#contact" class="text-white hover:text-teal-300 text-xl">Contacto</a>
        </div>
      </nav>

      <!-- Hero -->
      <div class="flex flex-col lg:flex-row items-center justify-between">
        <!-- Texto -->
        <div class="max-w-xl w-full px-1 sm:px-6 lg:px-0 mt-10 lg:mt-0 lg:ml-16 text-center lg:text-left">
        <span class="machine text-2xl sm:text-3xl lg:text-5xl font-josefin font-bold mb-6 block text-center">
          ¡Hola, Soy Samuel Membreño!</span>
          <h2 class="gsap-button text-2xl sm:text-3xl lg:text-4xl font-semibold mb-8 bg-gradient-to-r from-[#0CFFFF] via-[#dc0025] to-[#100425] bg-clip-text text-transparent">
            Desarollador Full Stack
          </h2>
          <p class="gsap-button text-base sm:text-lg lg:text-xl text-gray-300 mb-5 leading-relaxed">
            Con formación en un 
            técnico de grado superior
            en desarrollo de aplicaciones web (DAW).<br /><br />
          </p>
          <div class="flex flex-col lg:flex-row items-center">
            <div class="grid sm:grid-cols-4 gap-4">

              <a href="https://github.com/ssmembreno" target="_blank" 
              class="gsap-button border-3 border-solid text-white font-bold px-6 py-2 rounded-full shadow hover:border-teal-300 transition
               duration-300 text-center">Github</a>

              <a href="https://www.linkedin.com/public-profile/settings?trk=d_flagship3_profile_self_view_public_profile" target="_blank" 
              class=" gsap-button border-3 border-solid text-white font-bold px-6 py-2 rounded-full shadow hover:border-teal-300 transition 
              duration-300 text-center">LinkedIn</a>

              <a href="https://www.infojobs.net/candidate/cv/view/index.xhtml" target="_blank" 
              class="gsap-button border-3 border-solid text-white font-bold px-6 py-2 rounded-full shadow hover:border-teal-300 transition 
              duration-300 text-center">Infojobs</a>

              <a download="Samuel-Membreño_CV.pdf" href="/Sebastian-Samuel-membreño.pdf" target="_blank" 
              class="gsap-button border-3 border-solid text-white font-bold px-6 py-2 rounded-full shadow hover:border-teal-300 transition
               duration-300 text-center">CV</a>

            </div>
          </div>
        </div>

        <!-- Arrows icon-->
        <img
          src="/public/img//icons/arrow.png"
          alt="Flechas hacia abajo"
          class="absolute bottom-0 left-1/2 transform -translate-x-1/2 w-13 animate-bounce "
        />

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
              w-8 h-8 sm:w-9 sm:h-9 md:w-10 md:h-10 toast"
          />

          <!-- Imagen principal -->
          <img
            src="/public/img/samuel.png"
            alt="Samuel"
            class="w-full h-auto object-contain relative z-10 mb-30 toast"
          />

            <!-- CSS Icon -->
            <img
            src="/public/img/icons/css-3.png"
            alt="CSS"
            class="floating absolute z-20
                bottom-[100px]
                right-[5px] sm:right-[25px] md:right-[30px] lg:right-[10px]
                w-8 h-8 sm:w-9 sm:h-9 md:w-10 md:h-10 toast"
            />
        </div>
      </div>

      <!-- Backgrounds -->

      <div class="absolute inset-1 bg-grid opacity-20 pointer-events-none"></div>

    </section>
  </div>
</template>

<script setup lang="js">
const heroBackground = `
  background-image: linear-gradient(
    to top,
    rgba(15, 17, 38, 0.1) 0%,
    rgba(220, 0, 37, 0.2) 35%,
    rgba(86, 226, 210, 0.2) 80%,
    rgba(31, 27, 84, 0.3) 100%
  );
`;


  document.addEventListener("DOMContentLoaded", () => {
    gsap.fromTo(".gsap-button",
      {
        x: -2800,
        opacity: 100,
        rotate: 0
      },
      {
        x: 10,
        opacity: 100,
        rotate: 360,
        duration: 1,
        ease: "power2.out",
        yoyo: true,
        stagger: 0.15
      }
    );
  });
</script>

<style>
@media (max-width: 1024px) and (min-width: 768px) {
  img[alt="Flechas hacia abajo"] {
    display: none;
  }
}

@media (max-width: 767px) and (min-width: 480px) {
  img[alt="Flechas hacia abajo"] {
    display: none;
  }
}

@media (max-width: 479px) {
  img[alt="Flechas hacia abajo"] {
    display: none;
  }
}
</style>

