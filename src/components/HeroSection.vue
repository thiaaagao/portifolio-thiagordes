<script setup>
</script>

<template>
  <section class="hero" id="hero">
    <div class="hero-bg"></div>
    <div class="hero-content">
      <h1 class="hero-name">Thiago Rodrigues da Silva</h1>
      <p class="hero-title">IT Support Specialist (Tier 2/3) | Infraestrutura, Segurança e Desenvolvimento</p>
      <div class="hero-ctas">
        <a href="https://wa.me/5575991057716" target="_blank" rel="noopener noreferrer" class="btn btn-primary">
          <i class="ph-whatsapp-logo"></i> WhatsApp
        </a>
        <a href="mailto:rdes.thiago@gmail.com" class="btn btn-glass">
          <i class="ph-envelope"></i> Email
        </a>
        <a href="https://github.com/thiaaagao" target="_blank" rel="noopener noreferrer" class="btn btn-glass">
          <i class="ph-github-logo"></i> GitHub
        </a>
        <a href="https://www.linkedin.com/in/rdesthiago/" target="_blank" rel="noopener noreferrer" class="btn btn-glass">
          <i class="ph-linkedin-logo"></i> LinkedIn
        </a>
      </div>
    </div>
    <div class="scroll-indicator">
      <i class="ph-caret-down"></i>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  padding: 120px 20px 80px;
}

.hero-bg {
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at 50% 0%, rgba(34, 211, 238, 0.08) 0%, transparent 60%),
              radial-gradient(ellipse at 80% 50%, rgba(34, 211, 238, 0.04) 0%, transparent 50%);
  animation: heroGlow 8s ease-in-out infinite alternate;
}

@keyframes heroGlow {
  0% { opacity: 0.6; }
  100% { opacity: 1; }
}

.hero-content {
  position: relative;
  z-index: 1;
  text-align: center;
  max-width: 700px;
}

.hero-badge {
  display: inline-block;
  padding: 8px 20px;
  border-radius: 100px;
  font-size: 0.85rem;
  color: var(--accent);
  font-weight: 500;
  margin-bottom: 24px;
}

.hero-name {
  font-family: var(--font-title);
  font-size: 3rem;
  color: var(--text-primary);
  font-weight: 500;
  letter-spacing: 2px;
  margin-bottom: 16px;
  line-height: 1.2;
}

.hero-title {
  font-size: 1.1rem;
  color: var(--text-muted);
  margin-bottom: 40px;
  line-height: 1.6;
}

.hero-ctas {
  display: flex;
  gap: 12px;
  justify-content: center;
  flex-wrap: wrap;
}

.scroll-indicator {
  position: absolute;
  bottom: 40px;
  left: 50%;
  transform: translateX(-50%);
  color: var(--text-muted);
  font-size: 1.5rem;
  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
  40% { transform: translateX(-50%) translateY(-10px); }
  60% { transform: translateX(-50%) translateY(-5px); }
}

@media (max-width: 768px) {
  .hero-name {
    font-size: 2rem;
  }

  .hero-title {
    font-size: 0.95rem;
  }

  .hero-ctas {
    flex-direction: column;
    align-items: center;
  }
}
</style>
