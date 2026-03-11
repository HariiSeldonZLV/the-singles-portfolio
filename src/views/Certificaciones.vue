<template>
  <v-container class="py-12" style="display:flex; justify-content:center; align-items:center; flex-direction:column;">

    <!-- Flecha volver al Home -->
    <div class="back-home-arrow" @click="goHome"></div>

    <!-- Card central con estudios -->
    <v-card class="dark-card" outlined style="max-width:600px; width:100%;">
      <v-card-title class="doto red-title justify-center">
        <v-icon left color="#ff4d4d">mdi-school</v-icon>
        Estudios / Capacitación / Cursos
      </v-card-title>

      <v-card-text class="montserrat white-text">
        <ul>
          <li>
            <!-- Ícono destacado Front-End -->
            <v-icon left size="24" color="#ff4d4d">mdi-web</v-icon>
            Desarrollo Front-End Junior – Bootcamp SENCE
          </li>
          <li>
            <v-icon left small color="#ff4d4d">mdi-cog</v-icon>
            Técnico en Mantenimiento Electrónico – Instituto Lecciona
          </li>
          <li>
            <v-icon left small color="#ff4d4d">mdi-desktop-classic</v-icon>
            Técnico en Informática – Instituto IACC
          </li>
          <li>
            <v-icon left small color="#ff4d4d">mdi-laptop</v-icon>
            PMER Officer – Doutshes Rotes Kreuz, Berlin, Deutschland
          </li>
          <li>
            <v-icon left small color="#ff4d4d">mdi-school</v-icon>
            Derecho – Universidad de Valparaíso (8 semestres cursados)
          </li>
        </ul>
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
.white-text { color: #fff !important; }

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
