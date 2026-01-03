<template>
  <section class="relative bg-[#0f1126] py-26 px-6 md:px-20 text-white overflow-hidden min-h-screen flex flex-col items-center justify-center">
    <a id="about"></a>

    
    <!-- Foto circular -->
    <div class="relative z-10">
      <img src="/img/Samuel_Membreño_pic.png" alt="Samuel Membreño" class="w-66 h-66 rounded-full object-cover border-4shadow-lg" />
    </div>


    <div class="max-w-3xl relative z-10 text-center">

        <p class="mt-8 text-lg text-gray-300 leading-relaxed">
            Actualmente, sigo ampliando mis habilidades en frontend con Vue3
            y otras tecnologías para ofrecer soluciones completas y profesionales.
            Me considero una persona responsable, carismática, con muchas ganas de trabajar. 
            Me encanta aprender y crecer como desarrollador, siempre buscando aplicar buenas prácticas y ofrecer lo mejor de mi en cada proyecto con las siguientes tegnologias.
        </p>
    </div>


    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-2 lg:grid-cols-3 gap-6 mt-12">
            <!-- CARD -->
            <div class="relative group bg-white dark:bg-gray-800 rounded-2xl shadow-lg p-4 sm:p-6">
                <!-- Gradiente al pasar el cursor -->
                <div class="absolute inset-0 flex items-center justify-center pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity duration-500">
                    <div class="w-[300px] h-[200px] rounded-full bg-cyan-500/20 blur-3xl"></div>
                </div>
                <!-- Contenido -->
                <h2 class="text-lg sm:text-xl font-bold mb-4 text-center text-gray-800 dark:text-white">Frontend</h2>
                <div class="grid grid-cols-3 gap-4 justify-items-center relative z-10">
                    <img src="/img/icons/teg/001-html-5.png" alt="HTML5" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/007-css-3.png" alt="CSS3" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/003-js.png" alt="JavaScript" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/vue.png" alt="Vue" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/002-bootstrap.png" alt="Bootstrap" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/tailwind.png" alt="Tailwind" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/vite_icon.png" alt="Vite" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/blade_icon.png" alt="Blade" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                </div>
            </div>

    
            <!-- Card 2: Backend -->
            <div class="relative group bg-white dark:bg-gray-800 rounded-2xl shadow-lg p-4 sm:p-6">
                <div class="absolute inset-0 flex items-center justify-center pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity duration-500">
                    <div class="w-[300px] h-[200px] rounded-full bg-cyan-500/20 blur-3xl"></div>
                </div>
                <h2 class="text-lg sm:text-xl font-bold mb-4 text-center text-gray-800 dark:text-white">Backend</h2>
                <div class="grid grid-cols-3 gap-4 justify-items-center">
                    <img src="/img/icons/teg/laravel.png" alt="Laravel" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/005-php.png" alt="PHP" class="w-10 h-10 sm:w-14 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/006-mysql.png" alt="MySQL" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/mariaDB_icon.png" alt="MariaDB" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/004-java.png" alt="Java" class="w-10 h-10 sm:w-14 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/python_icon.png" alt="Python" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                </div>
            </div>

            <!-- Card 4: Herramientas -->
            <div class="relative group bg-white dark:bg-gray-800 rounded-2xl shadow-lg p-4 sm:p-6">
                <div class="absolute inset-0 flex items-center justify-center pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity duration-500">
                    <div class="w-[300px] h-[200px] rounded-full bg-cyan-500/20 blur-3xl"></div>
                </div>
                <h2 class="text-lg sm:text-xl font-bold mb-4 text-center text-gray-800 dark:text-white">Herramientas</h2>
                <div class="grid grid-cols-3 gap-4 justify-items-center">
                    <img src="/img/icons/teg/icons8-git-144.png" alt="Git" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/icons8-github-256.png" alt="GitHub" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/wordpress.png" alt="WordPress" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/postman.png" alt="Postman" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/VSC.png" alt="VS Code" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/icons8-aws-96.png" alt="AWS" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/linux.png" alt="Linux" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                    <img src="/img/icons/teg/docker.png" alt="Docker" class="w-10 h-10 sm:w-12 sm:h-12 transition-transform duration-300 transform group-hover:scale-105 hover:scale-110" />
                </div>
            </div>
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

</script>


