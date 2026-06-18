<script setup>
const infoCards = [
  { icon: "ph-graduation-cap", label: "MBA", value: "Seguran\u00e7a da Informa\u00e7\u00e3o — Cruzeiro do Sul" },
  { icon: "ph-graduation-cap", label: "Bacharel", value: "Sistemas da Informa\u00e7\u00e3o — FSSS" },
  { icon: "ph-graduation-cap", label: "T\u00e9cnico", value: "Inform\u00e1tica — IFBA" },
  { icon: "ph-map-pin", label: "Localiza\u00e7\u00e3o", value: "Cama\u00e7ari, Bahia" }
]
</script>

<template>
  <section class="section" id="sobre">
    <div class="container">
      <h2 class="section-title">Sobre Mim</h2>
      <div class="sobre-grid">
        <div class="sobre-texto glass">
          <p>
            Profissional de TI com experiência em Suporte técnico N1/N2, infraestrutura, IAM e SDM .
            Graduado em Sistemas da Informação pela FSSS e MBA em Segurança da Informação pela Cruzeiro do Sul.
          </p>
          <p>
            Fundador da <strong style="color: var(--accent);">Asatech</strong> — "Tecnologia que transforma negócios",
            empresa focada em soluções digitais para PMEs e MEIs na Região Metropolitana de Salvador, Bahia.
          </p>
          <p>
            Voluntário na <strong style="color: var(--accent);">RoadSec Salvador</strong>, festival de hacking e segurança,
            contribuindo com a comunidade de cibersegurança.
          </p>
        </div>
        <div class="sobre-info">
          <div class="sobre-card glass" v-for="card in infoCards" :key="card.label">
            <i :class="card.icon" style="font-size: 1.5rem; color: var(--accent);"></i>
            <div>
              <h4>{{ card.label }}</h4>
              <p>{{ card.value }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.sobre-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  gap: 32px;
  align-items: start;
}

.sobre-texto {
  padding: 32px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.sobre-texto p {
  font-size: 1rem;
  line-height: 1.7;
}

.sobre-info {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.sobre-card {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 16px 20px;
}

.sobre-card h4 {
  color: var(--text-primary);
  font-size: 0.9rem;
  font-weight: 600;
  margin-bottom: 2px;
}

.sobre-card p {
  color: var(--text-muted);
  font-size: 0.85rem;
}

@media (max-width: 768px) {
  .sobre-grid {
    grid-template-columns: 1fr;
  }
}
</style>
