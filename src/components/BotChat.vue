<template>
  <div class="fixed bottom-4 right-4 z-50 flex flex-col items-end">
    <!-- Mensaje de bienvenida (6s) -->
    <div v-if="showWelcome"
         class="mb-3 px-4 py-2 rounded-lg shadow animate-fade
                bg-gradient-to-r from-[#0CFFFF] to-[#ffd1d1] text-black max-w-xs text-sm">
      ¡Hola, soy SESAM 😊<br />
      Te ayudo a responder dudas sobre Samuel!
    </div>

    <!-- Botón/imagen del bot (oculto si el chat está abierto) -->
    <button v-if="!open"
            @click="open = true"
            class="rounded-full shadow p-0 border-0 bg-transparent">
      <img src="/img/Chatbot.png" alt="Chat" class="w-20 h-20" />
    </button>

    <!-- Ventana de chat -->
    <div v-if="open"
         class="w-80 h-96 mt-2 p-3 rounded-xl shadow bg-white/90 backdrop-blur
                bg-gradient-to-br from-cyan-300 to-rose-300 flex flex-col">
      <!-- Header con título y botón de cierre -->
      <div class="flex items-center justify-between mb-2">
        <div class="font-semibold text-slate-900">SESAM</div>
        <button @click="closeChat"
                aria-label="Cerrar chat"
                class="w-8 h-8 rounded-full grid place-items-center
                       hover:bg-black/10 active:scale-95 transition">
          ✕
        </button>
      </div>

      <!-- Mensajes -->
      <div ref="list" class="flex-1 overflow-auto space-y-2 text-sm">
        <div v-for="(m,i) in messages" :key="i"
             :class="m.role==='user' ? 'text-right' : 'text-left'">
          <span class="inline-block px-3 py-2 rounded-lg"
                :class="m.role==='user' ? 'bg-gray-200' : 'bg-blue-100'">
            {{ m.content }}
          </span>
        </div>
      </div>

      <!-- Input -->
      <form @submit.prevent="send" class="mt-2 flex items-center gap-2">
        <input v-model="input" class="flex-1 border rounded px-5 py-1"
               placeholder="Pregúntame algo..." />
        <button class="w-10 h-10 flex items-center justify-center">
          <img src="/img/icons/send.png" alt="" class="w-6 h-6 " />
        </button>
      </form>
    </div>
  </div>
</template>

<script setup>
import { ref, onUpdated, onMounted, onBeforeUnmount } from 'vue'

// Base de conocimiento simple
const KB = [
  { q: ['hola', 'Hola','hoal','que haces', 'Que Haces', 'Que haces', 'Que puedes hacer?','¿Que puedes hacer?',' ¿que puedes hacer?',' que puedes hacer?'], a: '¡Hola! Puedes preguntarme informacion sobre Samuel y te ayudare sin problema 😊' },

  {     q: [
      'quién eres','quien eres','presentación','presentacion','sobre ti','bio','biografía','biografia',
      'perfil','perfil profesional','resumen profesional','háblame de ti','hablame de ti',
      'qué te distingue','que te distingue','rol principal','en qué trabajas ahora','en que trabajas ahora',
      'servicios que ofreces','freelance','empleado','nivel profesional','disponibilidad actual'
    ],
     a: 'Soy Samuel tengo 20 años, desarrollador web titulado en un grado superior de desarrollo de aplicaiónes web (DAW), cuento con conocimientos en desarrollo full stack pero me enfoco mayormente en el desarrollo back end.' 
  },
    {
    q:[
     'a qué te dedicas','a que te dedicas','qué te gusta construir',
     'que te gusta construir',
    ],
    a: 'Me dedico a desarrollar/mantener aplicaciones web, me gusta construir diferente tipos de aplicaciones que pongan aprueba mis habilidades (APIs REST, front end con buen UX, gestores, blogs, SEO, panelesa administrativos)'
  },
  {
    q:[
    'tu trayectoria','trayectoria'
    ],
    a: 'Cuento con 1 año de experiencia, he trabajado como freelancer en diferentes proyectos, como principal trabaje en la correduria de seguros Infinity Brokers desarrollando y mejorando funcionalidades en el sistema, tanto de back end como de front end. He trabajado tambien en el desarrollo de paginas web en wordpress desarrollando mejoras visuales y adaptandola a que sea totalmente responsive y implementando nuevas funcionalidades. Tambien pase por INDRA donde realice mis practicas profesionales trabajando en la tegnologia APPIAN (low code).'
  },
  { q: ['tecnologías','stack','skills'], a: 'Trabajo con HTML, CSS3, JavaScript, PHP, Laravel 12, Vue 3, MySQL, Tailwind, WordPress, GIt GitHub y mas ' },

  { q: ['proyectos','portfolio','trabajos'], a: 'He desarrollado una galería de arte (Laravel), Pedals (Appian), actualmente me encuentro desarrollando FISCAPE una aplicacion para el control de finanzas personales.' },

  { q: ['experiencia','laboral'], a: 'Cuento con 1 año de experiencia, trabajando de manera freelancer en diferentes proyectos como Infinity Brokers, Ls Fitness, Galeria arte Enmanuel Membreño' },

  { q: ['contacto','email','contratar'], a: 'Puedes escribirme a samuel.mem123@gmail.com, Telefono: +34 641552638 o por LinkedIn https://www.linkedin.com/in/samuel-membre%C3%B1o/.' },
]

// Matcher muy simple
function answerFor(text){
  const t = text.toLowerCase()
  let best = null, scoreBest = 0
  for (const item of KB){
    let score = 0
    for (const k of item.q){
      const tokens = k.toLowerCase().split(/\s+/)
      const hits = tokens.filter(tok => t.includes(tok)).length
      score = Math.max(score, hits / tokens.length)
    }
    if (score > scoreBest){ scoreBest = score; best = item }
  }
  if (scoreBest >= 0.5) return best.a
  return "No tengo información sobre eso 😭. Preguntame cosas como que experiencia tiene, stack actual, biografia"
}

const open = ref(false)
const input = ref('')
const messages = ref([
  { role:'assistant', content:'¡Hola! Soy el bot de mi portafolio. Pregúntame sobre mis skills, proyectos o cómo contactar.' }
])

function send(){
  const text = input.value?.trim()
  if (!text) return
  messages.value.push({ role:'user', content:text })
  const a = answerFor(text)
  messages.value.push({ role:'assistant', content:a })
  input.value = ''
}

// Autoscroll
const list = ref(null)
onUpdated(()=>{ if(list.value){ list.value.scrollTop = list.value.scrollHeight } })

const showWelcome = ref(true)
onMounted(()=>{
  setTimeout(()=>{ showWelcome.value = false }, 6000)

  // Cerrar con Esc
  window.addEventListener('keydown', onKeydown)
})
onBeforeUnmount(()=>{
  window.removeEventListener('keydown', onKeydown)
})

function onKeydown(e){
  if (e.key === 'Escape') closeChat()
}

function closeChat(){
  open.value = false
}
</script>

<style scoped>
@keyframes fadeOut {
  0% { opacity: 1; }
  90% { opacity: 1; }
  100% { opacity: 0; }
}
.animate-fade {
  animation: fadeOut 6s forwards;
}
</style>
