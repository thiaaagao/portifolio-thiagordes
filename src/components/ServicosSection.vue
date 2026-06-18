<script setup>
const servicos = [
  {
    icon: "ph-globe",
    title: "Presen&ccedil;a Digital Essencial",
    desc: "Site institucional profissional com dom&iacute;nio, hospedagem e design responsivo.",
    price: "R$ 1.800 &uacute;nico"
  },
  {
    icon: "ph-rocket",
    title: "Produtividade M&aacute;xima",
    desc: "Automa&ccedil;&atilde;o de processos, ferramentas colaborativas e otimiza&ccedil;&atilde;o de fluxos.",
    price: "R$ 2.000/m&ecirc;s"
  },
  {
    icon: "ph-shield-check",
    title: "Seguran&ccedil;a para PMEs",
    desc: "Diagn&oacute;stico de vulnerabilidades, pol&iacute;ticas de seguran&ccedil;a e prote&ccedil;&atilde;o de dados.",
    price: "R$ 2.500 setup + R$ 500/m&ecirc;s"
  },
  {
    icon: "ph-chalkboard",
    title: "Treinamento Sob Medida",
    desc: "Capacita&ccedil;&atilde;o em TI, seguran&ccedil;a e ferramentas digitais para equipes.",
    price: "a partir de R$ 1.000"
  },
  {
    icon: "ph-robot",
    title: "Agentes de IA",
    desc: "Assistentes inteligentes e automa&ccedil;&atilde;o com intelig&ecirc;ncia artificial.",
    price: "Sob consulta"
  }
]
</script>

<template>
  <section class="section" id="servicos">
    <div class="container">
      <h2 class="section-title">Servi&ccedil;os</h2>
      <div class="serv-grid">
        <div class="glass servico-card" v-for="s in servicos" :key="s.title">
          <i :class="s.icon" style="font-size: 2rem; color: var(--accent);"></i>
          <h3 class="serv-title">{{ s.title }}</h3>
          <p class="serv-desc">{{ s.desc }}</p>
          <span class="serv-price">{{ s.price }}</span>
          <a href="#contato" class="btn btn-glass serv-cta">Saiba mais</a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.serv-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}

.servico-card {
  padding: 32px 24px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  text-align: center;
  align-items: center;
}

.serv-title {
  font-family: var(--font-title);
  font-size: 1rem;
  color: var(--text-primary);
  font-weight: 500;
  letter-spacing: 1px;
}

.serv-desc {
  font-size: 0.9rem;
  color: var(--text-muted);
  line-height: 1.6;
  flex: 1;
}

.serv-price {
  font-family: var(--font-title);
  color: var(--accent);
  font-size: 1rem;
  font-weight: 500;
}

.serv-cta {
  margin-top: 8px;
  width: 100%;
  justify-content: center;
}

@media (max-width: 1024px) {
  .serv-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 640px) {
  .serv-grid {
    grid-template-columns: 1fr;
  }
}
</style>
