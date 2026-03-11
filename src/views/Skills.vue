<template>
  <v-container class="py-12" style="display:flex; justify-content:center; align-items:center; flex-direction:column;">

    <!-- Flecha volver al Home -->
    <div class="back-home-arrow" @click="goHome"></div>

    <!-- Card central con skills -->
    <v-card class="dark-card fade-in" outlined style="max-width:600px; width:100%;">
      <v-card-title class="doto red-title justify-center">
        <v-icon left>mdi-brain</v-icon>
        Habilidades y Aprendizajes
      </v-card-title>

      <v-card-text class="montserrat white-text">
        <p class="fade-in-item" style="animation-delay: 0.1s;">
          Durante mi formación en Front-End y el Bootcamp SENCE he adquirido conocimientos sólidos en:
        </p>
        <ul>
          <li class="fade-in-item" style="animation-delay: 0.2s;">
            <v-icon left small color="#ff4d4d">mdi-language-html5</v-icon>
            HTML5 – Estructura semántica y accesibilidad
          </li>
          <li class="fade-in-item" style="animation-delay: 0.3s;">
            <v-icon left small color="#ff4d4d">mdi-language-css3</v-icon>
            CSS3 – Flexbox, Grid, animaciones y responsive design
          </li>
          <li class="fade-in-item" style="animation-delay: 0.4s;">
            <v-icon left small color="#ff4d4d">mdi-vuejs</v-icon>
            Vue 3 – Composition API, directives, props, emits y reactividad
          </li>
          <li class="fade-in-item" style="animation-delay: 0.5s;">
            <v-icon left small color="#ff4d4d">mdi-language-javascript</v-icon>
            JavaScript – ES6+, fetch, async/await, arrays y objetos
          </li>
          <li class="fade-in-item" style="animation-delay: 0.6s;">
            <v-icon left small color="#ff4d4d">mdi-vuetify</v-icon>
            Vuetify – Componentes, layouts y personalización de temas
          </li>
          <li class="fade-in-item" style="animation-delay: 0.7s;">
            <v-icon left small color="#ff4d4d">mdi-git</v-icon>
            Git y GitHub – Control de versiones y colaboración
          </li>
          <li class="fade-in-item" style="animation-delay: 0.8s;">
            <v-icon left small color="#ff4d4d">mdi-fire</v-icon>
            Integración con APIs y consumo de datos dinámicos
          </li>
        </ul>

        <p class="fade-in-item" style="animation-delay: 0.9s;">
          Estos conocimientos me permiten construir aplicaciones web interactivas, mantenibles y escalables, siguiendo buenas prácticas de desarrollo moderno.
        </p>
      </v-card-text>
    </v-card>

  </v-container>
</template>

<script setup lang="ts">
import { useRouter } from "vue-router";
const router = useRouter();

function goHome() {
  router.push("/");
}
</script>

<style scoped>
.dark-card {
  background-color: #1a1a1a !important;
  padding: 20px;
  margin-top: 40px;
  transition: transform 0.3s;
}
.dark-card:hover { transform: scale(1.02); }

.doto { font-family: "Doto", sans-serif !important; }
.montserrat { font-family: "Montserrat", sans-serif !important; }
.red-title { color: #ff4d4d !important; }
.white-text { color: #ffffff !important; }

/* Fade-in para la card */
.fade-in {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeUp 0.8s forwards;
  animation-delay: 0.1s;
}

/* Fade-in para elementos internos */
.fade-in-item {
  opacity: 0;
  transform: translateY(15px);
  animation: fadeUp 0.6s forwards;
}

@keyframes fadeUp {
  to { opacity: 1; transform: translateY(0); }
}

/* Flecha volver al home */
.back-home-arrow {
  position: fixed;
  bottom: 20px;
  left: 20px;
  width: 35px;
  height: 35px;
  border-top: 3px solid white;
  border-left: 3px solid white;
  transform: rotate(-45deg);
  cursor: pointer;
  animation: bounce 1.5s infinite;
  z-index: 1000;
  background: rgba(0,0,0,0.3);
  border-radius: 5px;
  padding: 5px;
}
@keyframes bounce {
  0%,20%,50%,80%,100% { transform: translateY(0) rotate(-45deg); }
  40% { transform: translateY(-6px) rotate(-45deg); }
  60% { transform: translateY(-3px) rotate(-45deg); }
}
.back-home-arrow:hover {
  border-color: #ff0000;
  background: rgba(255,0,0,0.2);
  transform: translateY(-2px) rotate(-45deg);
}
</style>
