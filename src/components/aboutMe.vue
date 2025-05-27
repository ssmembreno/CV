<template>
  <section class="relative bg-[#0f1126] py-26 px-6 md:px-20 text-white overflow-hidden min-h-screen flex flex-col items-center justify-center">
    
    <!-- Foto circular -->
    <div class="relative z-10">
      <img src="/img/Samuel-Membreño.jpeg" alt="Mi Foto" class="w-66 h-66 rounded-full object-cover border-4shadow-lg" />
    </div>

    <div class="max-w-3xl relative z-10 text-center">
        <p class="mt-8 text-lg text-gray-300 leading-relaxed">
            Soy un apasionado del desarrollo web, con 3 meses de experiencia laboral.
            Cuento con el título de Técnico Superior en Desarrollo de Aplicaciones Web (DAW) y Técnico en Sistemas Microinformáticos y Redes.
            He ido incrementando mis conocimientos de forma autodidacta desarrollando proyectos con Laravel, PHP, JavaScript y bases de datos.
        </p>

        <p class="mt-8 text-lg text-gray-300 leading-relaxed">
            Actualmente, sigo ampliando mis habilidades en frontend con Vue,
            Tailwind y otras tecnologías para ofrecer soluciones completas y profesionales.
            Me considero una persona responsable, carismática, con muchas ganas de trabajar. 
            Me encanta aprender y crecer como desarrollador, siempre buscando aplicar buenas prácticas y ofrecer lo mejor en cada proyecto.
        </p>
    </div>

    <div class="mt-12 flex flex-wrap justify-center gap-5 relative z-10">
        <img src="/img/icons/teg/001-html-5.png" alt="HTML5" class="w-12 h-12" />
        <img src="/img/icons/teg/007-css-3.png" alt="CSS3" class="w-12 h-12" />
        <img src="/img/icons/teg/003-js.png" alt="JavaScript" class="w-12 h-12" />
        <img src="/img/icons/teg/002-bootstrap.png" alt="Bootstrap" class="w-12 h-12" />   
        <img src="/img/icons/teg/tailwind.png" alt="Tailwind" class="w-12 h-12" /> 
        <img src="/img/icons/teg/004-java.png" alt="Java" class="w-12 h-12" />
        <img src="/img/icons/teg/005-php.png" alt="PHP" class="w-12 h-12" />
        <img src="/img/icons/teg/laravel.png" alt="Laravel" class="w-12 h-12" />
        <img src="/img/icons/teg/006-mysql.png" alt="MySQL" class="w-12 h-12" />
        <img src="/img/icons/teg/icons8-git-144.png" alt="Git" class="w-12 h-12" />
        <img src="/img/icons/teg/icons8-github-256.png" alt="GitHub" class="w-14 h-14" />
    </div>

    <!-- Fondo con gradiente circular -->
    <div class="absolute inset-0 flex items-center justify-center pointer-events-none">
      <div class="w-[650px] h-[650px] rounded-full bg-green-500/10 blur-3xl"></div>
    </div>

    <!-- Líneas de fondo -->
    <div class="absolute inset-1 bg-grid opacity-20 pointer-events-none"></div>
  </section>
</template>

<script setup lang="js">
// No necesitas JS por ahora
</script>


