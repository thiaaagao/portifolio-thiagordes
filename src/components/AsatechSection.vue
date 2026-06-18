<script setup>
</script>

<template>
  <section class="section" id="asatech">
    <div class="container">
      <div class="asa-wrapper">
        <div class="asa-preview glass">
          <div class="preview-bar">
            <span class="preview-dot"></span>
            <span class="preview-dot"></span>
            <span class="preview-dot"></span>
            <span class="preview-url">asatechti.netlify.app</span>
          </div>
          <div class="preview-frame">
            <iframe
              src="https://asatechti.netlify.app"
              title="Preview Asatech"
              loading="lazy"
              sandbox="allow-scripts allow-same-origin"
            ></iframe>
          </div>
          <a href="https://asatechti.netlify.app" target="_blank" rel="noopener noreferrer" class="preview-overlay">
            <span>Abrir site completo <i class="ph-arrow-up-right"></i></span>
          </a>
        </div>
        <div class="asa-card glass">
          <span class="asa-logo">ASATECH</span>
          <h2 class="asa-tagline">Tecnologia que Impulsiona seu Negócio</h2>
          <p class="asa-desc">
            Empresa de TI focada em PMEs e MEIs na Região Metropolitana de Salvador, Bahia.
            Oferecemos soluções no presencial e digital, produtividade, segurança e automação.
          </p>
          <div class="asa-contacts">
            <span><i class="ph-phone"></i> (71) 98393-6822</span>
            <span><i class="ph-envelope"></i> asatechti@gmail.com</span>
            <span><i class="ph-link"></i> CNPJ: 52.420.337/0001-51</span>
          </div>
          <a href="https://asatechti.netlify.app" target="_blank" rel="noopener noreferrer" class="btn btn-primary">
            <i class="ph-globe"></i> Conheça a Asatech
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.asa-wrapper {
  display: flex;
  flex-direction: column;
  gap: 32px;
  max-width: 700px;
  margin: 0 auto;
}

.asa-preview {
  overflow: hidden;
  display: flex;
  flex-direction: column;
  position: relative;
}

.preview-bar {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 12px 16px;
  border-bottom: 1px solid var(--border-glass);
  background: rgba(0, 0, 0, 0.2);
}

.preview-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: #ef4444;
}

.preview-dot:nth-child(2) {
  background: #f59e0b;
}

.preview-dot:nth-child(3) {
  background: #22c55e;
}

.preview-url {
  color: var(--text-muted);
  font-size: 0.75rem;
  margin-left: 8px;
  font-family: monospace;
}

.preview-frame {
  height: 400px;
  overflow: hidden;
  position: relative;
}

.preview-frame iframe {
  width: 100%;
  height: 100%;
  border: none;
  transform: scale(0.5);
  transform-origin: 0 0;
  width: 200%;
  height: 200%;
  pointer-events: none;
}

.preview-overlay {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.5);
  opacity: 0;
  transition: opacity 0.3s;
  color: white;
  font-weight: 600;
  font-size: 1rem;
  text-decoration: none;
}

.asa-preview:hover .preview-overlay {
  opacity: 1;
}

.preview-overlay span {
  display: flex;
  align-items: center;
  gap: 8px;
  background: var(--accent);
  color: var(--bg-primary);
  padding: 12px 24px;
  border-radius: 8px;
}

.asa-card {
  padding: 40px 32px;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.asa-logo {
  font-family: var(--font-title);
  font-size: 2rem;
  color: var(--accent);
  font-weight: 600;
  letter-spacing: 4px;
}

.asa-tagline {
  font-family: var(--font-title);
  font-size: 1.25rem;
  color: var(--text-primary);
  font-weight: 500;
  letter-spacing: 1px;
}

.asa-desc {
  color: var(--text-muted);
  font-size: 0.95rem;
  line-height: 1.7;
  max-width: 500px;
}

.asa-contacts {
  display: flex;
  gap: 24px;
  flex-wrap: wrap;
  justify-content: center;
  color: var(--text-secondary);
  font-size: 0.9rem;
}

.asa-contacts i {
  margin-right: 6px;
  color: var(--accent);
}

@media (max-width: 900px) {
  .preview-frame {
    height: 300px;
  }
}

@media (max-width: 640px) {
  .asa-card {
    padding: 32px 24px;
  }

  .asa-contacts {
    flex-direction: column;
    align-items: center;
  }

  .preview-frame {
    height: 240px;
  }
}
</style>
