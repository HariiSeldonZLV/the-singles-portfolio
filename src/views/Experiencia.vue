<template>
  <v-container class="py-12">

    <!-- Flecha volver al Home -->
    <div class="back-home-arrow" @click="goHome"></div>

    <!-- Título -->
    <h1 class="doto red-title text-center mb-10">Experiencia</h1>

    <!-- Cards de experiencia + referencias -->
    <v-row justify="center" dense>
      <v-col
        v-for="(item, index) in allCards"
        :key="index"
        cols="12"
        md="6"
      >
        <v-card
          class="dark-card fade-in"
          outlined
          :style="{ animationDelay: `${0.15 * index}s` }"
        >
          <v-card-title class="doto red-title">
            <v-icon v-if="item.icon" left>{{ item.icon }}</v-icon>
            {{ item.puesto }}
          </v-card-title>

          <v-card-subtitle v-if="item.empresa" class="montserrat red-subtitle">
            {{ item.empresa }} — {{ item.fecha }}
          </v-card-subtitle>

          <v-card-text class="montserrat white-text">
            <ul>
              <li v-for="(detail, i) in item.detalles || []" :key="i">{{ detail }}</li>
              <li v-for="(ref, i) in item.referencias || []" :key="i">
                <v-icon left small color="#ff4d4d">mdi-account</v-icon>
                {{ ref.nombre }} – {{ ref.contacto }}
              </li>
            </ul>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>

  </v-container>
</template>

<script setup lang="ts">
import { useRouter } from "vue-router";

const router = useRouter();
function goHome() { router.push("/"); }

// Experiencias
const experiencias = [
  {
    puesto: "Setter",
    empresa: "Agencia O3",
    fecha: "01/2026 – Presente",
    icon: "mdi-account-tie",
    detalles: ["Contacto de prospectos","Gestión agenda de ventas"]
  },
  {
    puesto: "Encargado de cámara, almacenaje y despacho",
    empresa: "Planta Campofrut",
    fecha: "Noviembre y diciembre 2025",
    icon: "mdi-factory",
    detalles: ["Encargado de cámara, almacenaje y despacho","Control de calidad","Recepción de fruta y entrada a proceso"]
  },
  {
    puesto: "Administrador General",
    empresa: "Supermercado Bodega Ahorro Talca",
    fecha: "Junio a Octubre 2025",
    icon: "mdi-store",
    detalles: ["Administrador General","Habilitación sistemas para venta y atención online","Reclutamiento de personal","Adquisiciones","Estrategias de venta","Puesta en marcha"]
  },
  {
    puesto: "Responsable de proyectos de tecnología en Seguridad Pública",
    empresa: "Ilustre Municipalidad de Molina",
    fecha: "2020 a 2024",
    icon: "mdi-shield-account",
    detalles: ["Responsable de proyectos de tecnología y mantenimiento de equipos de seguridad","Incorporando herramientas IA en la identificación de vehículos involucrados en hechos delictivos"]
  },
  {
    puesto: "Soporte para equipos de pago",
    empresa: "Haulmer TUU",
    fecha: "2019 a 2020",
    icon: "mdi-credit-card",
    detalles: ["Atención/soporte equipos de pago con tarjetas","Ventas","Onboarding sistemas de pago con tarjeta y DTE"]
  },
  {
    puesto: "Administrador Hotelero en Brasil",
    empresa: "Che Lagarto Suites Búzios y Pousada Beiramar",
    fecha: "2015 a 2016",
    icon: "mdi-hotel",
    detalles: ["Prestación de servicios como administrador en Che Lagarto Suites, Búzios, Rio de Janeiro, Brasil","Administrador en Pousada Beiramar, Búzios, Brasil"]
  },
  {
    puesto: "SAC / RRSS",
    empresa: "Grupo Transporte Pasajeros (GTP) TURBUS",
    fecha: "2016 a 2019",
    icon: "mdi-message-text",
    detalles: ["Servicio de Atención al cliente","Mensajería de RRSS, ventas, reservas y reclamos","Coordinación con flota en situaciones de emergencia en ruta"]
  },
  {
    puesto: "Project Manager",
    empresa: "Chilean Red Cross, IFRC & JRCS",
    fecha: "1996 a 2016",
    icon: "mdi-earth",
    detalles: [
      "Project mánager Japanese Red Cross Society de 2010 a 2012 para las comunidades costeras afectadas por tsunami de 2010",
      "Responsable de la unidad de Logística para Cruz Roja Chilena, responsable de la adquisición y control de flota nacional, distribución de ayuda humanitaria y despliegue de unidades en zonas de difícil acceso y en situaciones de riesgo",
      "Responsable del POA (Plan of Action) Terremoto Chile 2010, operación de Cruz Roja Internacional",
      "Responsable de equipo durante la habilitación y puesta en marcha del hospital de campaña San José de Parral donado por el Gobierno de Japón",
      "Traductor para delegaciones durante la operación de emergencia del 27 de Febrero de 2010",
      "Director de Albergues para personas en situación calle, siendo el más grande el Estadio Víctor Jara, más de 500 personas a diario"
    ]
  },
  // Nueva experiencia agregada
  {
    puesto: "Ventas Ecommerce / Gestión de Inventario",
    empresa: "María Soto / Boston Repuestos",
    fecha: "2016 a 2017",
    icon: "mdi-cart",
    detalles: [
      "Primer Ecommerce del Barrio 10 de Julio",
      "Nuevo sistema de inventario asociado al ecommerce",
      "Branding y cambio en la gestión de ventas"
    ]
  }
];

// Card de referencias
const referencias = {
  puesto: "Referencias",
  icon: "mdi-account-group",
  referencias: [
    { nombre: "Naoki Kokawa", contacto: "kokawanaoki@gmail.com" },
    { nombre: "Rafael Méndez Mella", contacto: "presidencia@cruzroja.cl – +56(2) 2783 4100" },
    { nombre: "Tomoko Niino", contacto: "tniino@yahoo.com" },
    { nombre: "Gustavo Ramírez Arriagada", contacto: "gustavo.ramirez@ifrc.org" },
    { nombre: "Fernando Uribe-Etxeverria", contacto: "furibe@uribe-etxeverria.cl – +56 (2) 26952210" },
    { nombre: "Dante Torres Ibarra", contacto: "dante@o3.cl" }
  ]
};

// Unimos todo en un solo array para animación cascada
const allCards = [...experiencias, referencias];
</script>

<style scoped>
.dark-card {
  background-color: #1a1a1a !important;
  margin-bottom: 20px;
  transition: transform 0.3s;
}
.dark-card:hover { transform: scale(1.02); }

/* Animación fade-in en cascada */
.fade-in {
  opacity: 0;
  transform: translateY(25px);
  animation: fadeUpCascade 0.8s forwards;
  animation-timing-function: ease-out;
}

@keyframes fadeUpCascade {
  0% { opacity: 0; transform: translateY(25px); }
  60% { opacity: 0.7; transform: translateY(-5px); }
  100% { opacity: 1; transform: translateY(0); }
}

.doto { font-family: "Doto", sans-serif !important; }
.montserrat { font-family: "Montserrat", sans-serif !important; }
.red-title { color: #ff4d4d !important; }
.red-subtitle { color: #ff4d4d !important; }
.white-text { color: #ffffff !important; }

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
