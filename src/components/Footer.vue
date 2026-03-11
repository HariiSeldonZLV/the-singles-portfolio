<template>
  <v-footer padless class="footer-background">
    <v-container class="d-flex flex-column align-center py-0.5">
      <div class="social-icons mb-0">
        <a href="https://www.facebook.com/denis.salinas" target="_blank" rel="noopener noreferrer" class="social-icon">
          <v-icon size="36">mdi-facebook</v-icon>
        </a>
        <a href="https://www.instagram.com/denis.salinas/" target="_blank" rel="noopener noreferrer" class="social-icon">
          <v-icon size="36">mdi-instagram</v-icon>
        </a>
        <a href="https://www.linkedin.com/in/denis-salinas-49b6b352/" target="_blank" rel="noopener noreferrer" class="social-icon">
          <v-icon size="36">mdi-linkedin</v-icon>
        </a>
      </div>

      <div class="creator-info">
        &copy; 2026 Denis Salinas — Molina, Región del Maule, Chile
      </div>

      <div class="portfolio-legend">
        Portafolio inspirado en <strong>The Singles 81-98</strong> de Depeche Mode
      </div>
    </v-container>
  </v-footer>
</template>

<script setup lang="ts"></script>

<style scoped>
.footer-background {
  background-color: rgba(17,17,17,0.95);
  color: white;
  border-top: 1px solid #ff0000;
  text-align: center;

  display: flex;
  flex-direction: column;
  justify-content: center;
  min-height: 50px; /* ultracompacto */
}

.social-icons {
  display: flex;
  justify-content: center;
  gap: 12px;
}

.social-icon {
  color: white;
  transition: all 0.3s ease;
}

.social-icon:hover {
  color: #ff0000;
  transform: scale(1.1);
}

.creator-info {
  font-size: 11px;
  opacity: 0.8;
  margin: 0;
}

.portfolio-legend {
  font-size: 10px;
  opacity: 0.7;
  margin: 0;
}

/* Responsive */
@media (max-width: 600px) {
  .footer-background { min-height: 45px; }
  .social-icons { gap: 8px; }
  .creator-info { font-size: 10px; }
  .portfolio-legend { font-size: 9px; }
}
</style>
