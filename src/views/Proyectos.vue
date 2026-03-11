<template>
  <v-container class="py-12">

    <!-- FLECHA FIJA VOLVER AL HOME -->
    <div
      class="back-home-arrow"
      v-if="!isHomePage"
      @click="goHome"
    ></div>

    <!-- Sección Proyecto Web -->
    <v-row justify="center" class="mb-12">
      <v-col cols="12" md="6">
        <v-card class="dark-card" outlined>
          <!-- Mockup de laptop realista -->
          <div class="mockup-laptop-real">
            <div class="mockup-screen-wrapper">
              <img
                :src="maulenoticiasImg"
                alt="Captura Maulenoticias"
                class="mockup-screen"
              />
              <div class="mockup-reflection"></div>
            </div>
          </div>

          <!-- Títulos y descripción -->
          <v-card-title class="doto red-title justify-center">
            Proyecto Maulenoticias2
          </v-card-title>

          <v-card-subtitle class="montserrat red-subtitle text-center">
            Sitio web de noticias desarrollado como proyecto personal
          </v-card-subtitle>

          <v-card-text class="montserrat white-text text-center">
            Revisa el proyecto completo y explora noticias actualizadas.
          </v-card-text>

          <v-card-actions class="justify-center">
            <v-btn
              color="primary"
              href="https://hariiseldonzlv.github.io/maulenoticias2/#/"
              target="_blank"
            >
              Ver Proyecto
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>

    <!-- Sección Videos Humanitarios -->
    <h2 class="doto red-title text-center mb-6">Proyectos Humanitarios</h2>
    <v-row justify="center" dense>
      <v-col cols="12" md="4" v-for="(video, index) in videos" :key="index">
        <v-card class="dark-card" outlined>
          <iframe
            :src="`https://www.youtube.com/embed/${video.id}`"
            height="200"
            frameborder="0"
            allowfullscreen
            class="video-frame"
          ></iframe>
          <v-card-title class="doto red-title">{{ video.title }}</v-card-title>
          <v-card-text class="montserrat white-text">{{ video.desc }}</v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup lang="ts">
import maulenoticiasImg from "@/assets/maulenoticias.png";
import { useRouter, useRoute } from "vue-router";

const router = useRouter();
const route = useRoute();
const isHomePage = route.path === "/" || route.path === "/the-singles-portfolio/";

function goHome() {
  router.push("/");
}

const videos = [
  {
    title: "Medios de vida pesqueros",
    id: "58VOpib2BaI",
    desc: "Proyecto humanitario enfocado en medios de vida pesqueros en comunidades locales."
  },
  {
    title: "Medios de vida apicultura",
    id: "MM1rrrzJgXk",
    desc: "Desarrollo de iniciativas de apicultura para mejorar ingresos de familias rurales."
  },
  {
    title: "Red para reconstrucción",
    id: "4wj9yxXswqQ",
    desc: "Coordinación de proyectos de reconstrucción y ayuda post-desastres naturales."
  }
];
</script>

<style scoped>
/* FLECHA FIJA VOLVER AL HOME */
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
  z-index: 1000; /* siempre encima */
  background: rgba(0,0,0,0.3);
  border-radius: 5px;
  padding: 5px;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateY(0) rotate(-45deg); }
  40% { transform: translateY(-6px) rotate(-45deg); }
  60% { transform: translateY(-3px) rotate(-45deg); }
}

/* Efecto hover */
.back-home-arrow:hover {
  border-color: #ff0000;
  background: rgba(255,0,0,0.2);
  transform: translateY(-2px) rotate(-45deg);
}

/* Card oscuro */
.dark-card {
  background-color: #1a1a1a !important;
  transition: transform 0.3s;
}
.dark-card:hover {
  transform: scale(1.03);
}

/* Fuentes y colores */
.doto {
  font-family: "Doto", sans-serif !important;
}
.montserrat {
  font-family: "Montserrat", sans-serif !important;
}
.red-title {
  color: #ff4d4d !important;
}
.red-subtitle {
  color: #ff4d4d !important;
}
.white-text {
  color: #ffffff !important;
}

/* Mockup laptop realista */
.mockup-laptop-real {
  position: relative;
  width: 100%;
  padding-top: 56.25%;
  margin-bottom: 16px;
}

.mockup-screen-wrapper {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 8px solid #222;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 12px 25px rgba(0,0,0,0.6);
  background: #111;
}

.mockup-screen {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.mockup-reflection {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(rgba(255,255,255,0.05), rgba(255,255,255,0.1));
  pointer-events: none;
}

/* Video full width */
.video-frame {
  width: 100%;
}
</style>
