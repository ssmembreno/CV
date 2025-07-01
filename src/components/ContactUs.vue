<template>
  <section class="relative bg-[#0f1126] py-26 px-6 md:px-20 text-white overflow-hidden flex flex-col md:flex-row justify-center items-center gap-15">
    
    <div class="max-w-md">
      <h2 class="text-4xl md:text-5xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-[#0CFFFF] via-[#dc0025] to-[#100425] mb-6">
        Contactame
      </h2>
      <a id="contact"></a>
      <p class="text-gray-300 mb-6">
        <strong>¿Te agrada mi perfil? </strong> <br> Déjame un mensaje en mi correo electrónico
     </p>

      <ul class="space-y-4">
        <li class="flex items-center gap-3">
          <span class="w-10 h-10 flex items-center justify-center bg-gradient-to-r from-[#0CFFFF] to-[#dc0025] rounded-full">
            <i class="fa fa-envelope text-xl"></i>
          </span>
          <span><a href="mailto:samuel.mem123@gmail.com">samuel.mem123@gmail.com</a></span>
        </li>
      </ul>
    </div>

    <div class="bg-[#181a2f] rounded-xl p-8 w-full max-w-md shadow-lg">
      <form @submit.prevent="sendEmail" class="space-y-6">
        <div>
          <label class="block mb-1 text-gray-400">Nombre</label>
          <input v-model="name" type="text" placeholder="John" required class="w-full p-3 rounded bg-[#0f1126] text-white border border-[#2a2c44] focus:outline-none focus:ring-2 focus:ring-[#00ffff]" />
        </div>
        <div>
          <label class="block mb-1 text-gray-400">Correo Electronico</label>
          <input v-model="email" type="email" placeholder="example@example.com" required  class="w-full p-3 rounded bg-[#0f1126] text-white border border-[#2a2c44] focus:outline-none focus:ring-2 focus:ring-[#00ffff]" />
        </div>
        <div>
          <label class="block mb-1 text-gray-400">Mensaje</label>
          <textarea v-model="message" placeholder="Escribe tu mensaje" required class="w-full p-3 rounded bg-[#0f1126] text-white border border-[#2a2c44] focus:outline-none focus:ring-2 focus:ring-[#00ffff]" rows="4"></textarea>
        </div>
        <button type="submit" class="w-full p-3 rounded bg-gradient-to-r from-[#0CFFFF] to-[#dc0025] text-white font-semibold hover:opacity-90 transition">
          Enviar
        </button>

        <p id="end" class="text-sm text-center text-white mt-4">{{ status }}</p>
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import emailjs from '@emailjs/browser'

const name = ref('')
const email = ref('')
const message = ref('')
const status = ref('')

const SERVICE_ID = 'service_z59xrmo'
const TEMPLATE_ID = 'template_xzsr7gc'
const PUBLIC_KEY = 'Clv5YzIZrpwzNcJzL'

const sendEmail = () => {
  const templateParams = {
    name: name.value,
    email: email.value,
    message: message.value
  }

  emailjs.send(SERVICE_ID, TEMPLATE_ID, templateParams, PUBLIC_KEY)
    .then(() => {
      status.value = '✅ ¡Mensaje enviado con éxito!'
      name.value = ''
      email.value = ''
      message.value = ''
    })
    .catch((error) => {
      console.error('Error al enviar:', error)
      status.value = '❌ Error al enviar el mensaje. Intenta más tarde.'
    })

      setTimeout(() => {
        status.value = ''
      }, 5000)

}
</script>

