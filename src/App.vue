<template>
  <v-app>
    <v-main class="app-background">
      <!-- Aquí se cargan todas las rutas -->
      <router-view />
    </v-main>

    <!-- Flecha volver al Home solo si no estamos en Home -->
    <div v-if="!isHomePage" class="back-home-arrow" @click="goHome"></div>

    <!-- Nota musical siempre presente -->
    <MiniSoundCloudPlayer />

    <!-- Footer siempre presente -->
    <Footer />
  </v-app>
</template>

<script setup lang="ts">
import { useRouter, useRoute } from "vue-router";
import { computed } from "vue";

import Footer from "./components/Footer.vue";
import MiniSoundCloudPlayer from "./components/MiniSoundCloudPlayer.vue";

const router = useRouter();
const route = useRoute();

// Detecta si estamos en Home
const isHomePage = computed(() => route.path === "/" || route.path === "/the-singles-portfolio/");

// Función para volver al Home
function goHome() {
  router.push("/");
}
</script>

<style>
/* Contenido principal */
.app-background {
  padding-top: 0;
  overflow: auto;
  background:
    linear-gradient(
      to bottom,
      #138ea4 0%,
      #138ea4 35%,
      rgba(252,176,69,0.35) 45%,
      #000000 65%,
      #000000 100%
    );
  position: relative;
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
