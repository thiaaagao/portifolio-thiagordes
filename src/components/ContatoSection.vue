<script setup>
const contatos = [
  { icon: "ph-whatsapp-logo", label: "WhatsApp", value: "(75) 99105-7716", url: "https://wa.me/5575991057716" },
  { icon: "ph-envelope", label: "Email", value: "rdes.thiago@gmail.com", url: "mailto:rdes.thiago@gmail.com" },
  { icon: "ph-github-logo", label: "GitHub", value: "/thiaaagao", url: "https://github.com/thiaaagao" },
  { icon: "ph-linkedin-logo", label: "LinkedIn", value: "Thiago Rodrigues", url: "https://www.linkedin.com/in/rdesthiago/" }
]
</script>

<template>
  <section class="section" id="contato">
    <div class="container">
      <h2 class="section-title">Contato</h2>
      <div class="contato-grid">
        <a class="glass contato-item" v-for="c in contatos" :key="c.label" :href="c.url" target="_blank" rel="noopener noreferrer">
          <i :class="c.icon" style="font-size: 2rem; color: var(--accent);"></i>
          <div>
            <h3 class="contato-label">{{ c.label }}</h3>
            <p class="contato-value">{{ c.value }}</p>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contato-grid {
  max-width: 600px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.contato-item {
  padding: 24px;
  display: flex;
  align-items: center;
  gap: 16px;
  cursor: pointer;
  transition: transform 0.3s, box-shadow 0.3s, border-color 0.3s;
}

.contato-item:hover {
  border-color: var(--accent-dim);
}

.contato-label {
  color: var(--text-primary);
  font-size: 1rem;
  font-weight: 600;
  margin-bottom: 4px;
}

.contato-value {
  color: var(--text-muted);
  font-size: 0.85rem;
}

@media (max-width: 640px) {
  .contato-grid {
    grid-template-columns: 1fr;
  }
}
</style>
