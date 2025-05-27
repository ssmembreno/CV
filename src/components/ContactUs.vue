<template>
  <section class="relative bg-[#0f1126] py-26 px-6 md:px-20 text-white overflow-hidden flex flex-col md:flex-row justify-center items-center gap-12">
    <!-- Izquierda: Información de contacto -->
    <div class="max-w-md">
      <h2 class="text-4xl md:text-5xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-[#0CFFFF] via-[#dc0025] to-[#100425] mb-6">
        Contactame
      </h2>
      <p class="text-gray-300 mb-6">
        <strong>¿Te agrada mi perfil? </strong> <br> Dejame un mensaje al correo o puedes utilizar mi numero de telefono :)
     </p>

      <ul class="space-y-4">
        <li class="flex items-center gap-3">
          <span class="w-10 h-10 flex items-center justify-center bg-gradient-to-r from-[#0CFFFF] to-[#dc0025] rounded-full">
            <i class="fa fa-phone text-xl"></i>
          </span>
          <span>+34 641-552-638</span>
        </li>
        <li class="flex items-center gap-3">
          <span class="w-10 h-10 flex items-center justify-center bg-gradient-to-r from-[#0CFFFF] to-[#dc0025] rounded-full">
            <i class="fa fa-envelope text-xl"></i>
          </span>
          <span>samuel.mem123@gmail.com</span>
        </li>
        <li class="flex items-center gap-3">
          <span class="w-10 h-10 flex items-center justify-center bg-gradient-to-r from-[#0CFFFF] to-[#dc0025] rounded-full">
            <i class="fa fa-map-marker text-xl"></i>
          </span>
          <span>Albacete Hellín, España</span>
        </li>
      </ul>
    </div>

    <!-- Derecha: Formulario -->
    <div class="bg-[#181a2f] rounded-xl p-8 w-full max-w-md shadow-lg">
      <form class="space-y-6">
        <div>
          <label class="block mb-1 text-gray-400">Nombre</label>
          <input type="text" placeholder="John" class="w-full p-3 rounded bg-[#0f1126] text-white border border-[#2a2c44] focus:outline-none focus:ring-2 focus:ring-[#00ffff]" />
        </div>
        <div>
          <label class="block mb-1 text-gray-400">Correo Electronico</label>
          <input type="email" placeholder="example@example.com" class="w-full p-3 rounded bg-[#0f1126] text-white border border-[#2a2c44] focus:outline-none focus:ring-2 focus:ring-[#00ffff]" />
        </div>
        <div>
          <label class="block mb-1 text-gray-400">Mensaje</label>
          <textarea placeholder="Escribe tu mensaje" class="w-full p-3 rounded bg-[#0f1126] text-white border border-[#2a2c44] focus:outline-none focus:ring-2 focus:ring-[#00ffff]" rows="4"></textarea>
        </div>
        <button type="submit" class="w-full p-3 rounded bg-gradient-to-r from-[#0CFFFF] to-[#dc0025] text-white font-semibold hover:opacity-90 transition">
          Enviar
        </button>
      </form>
    </div>

  </section>
</template>

<script setup>
// Font Awesome para íconos (si no tienes, puedes usar cualquier librería de íconos)
</script>

