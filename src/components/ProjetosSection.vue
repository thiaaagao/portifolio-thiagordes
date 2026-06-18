<script setup>
import { ref, onMounted } from "vue"

const featured = [
  {
    title: "Asatech PJ Landing Page",
    desc: "Landing page institucional da Asatech — site oficial da empresa.",
    stack: ["React", "TypeScript", "Tailwind"],
    gitUrl: "https://github.com/thiaaagao/asatech-landing-digital",
    liveUrl: "https://asatechti.netlify.app",
    icon: "ph-buildings"
  },
  {
    title: "Fã Site Cyberpunk TCG",
    desc: "Trading card game com temática cyberpunk.",
    stack: ["JavaScript"],
    gitUrl: "https://github.com/thiaaagao/cyberpunk-tcg",
    liveUrl: "https://cyberpunk-tcg-ten.vercel.app/",
    icon: "ph-sword"
  },
  {
    title: "FRP Bypass Recovery",
    desc: "Ferramenta para bypass de FRP em dispositivos Android.",
    stack: ["Python"],
    gitUrl: "https://github.com/thiaaagao/frp-bypass",
    liveUrl: null,
    icon: "ph-shield-check"
  },
  {
    title: "League Of Legends - Champion Page",
    desc: "App de consulta de campeões do League of Legends.",
    stack: ["JavaScript"],
    gitUrl: "https://github.com/thiaaagao/league-of-legends-champion",
    liveUrl: "https://thiaaagao.github.io/league-of-legends-champion/",
    icon: "ph-game-controller"
  },
  {
    title: "Pokedex CRUD",
    desc: "Pokédex com operações CRUD para gerenciar pokémons.",
    stack: ["JavaScript"],
    gitUrl: "https://github.com/thiaaagao/pokedexcrud",
    liveUrl: "https://thiaaagao.github.io/pokedexcrud/",
    icon: "ph-dog"
  }
]

const apiProjetos = ref([])
const loading = ref(true)

onMounted(async () => {
  try {
    const res = await fetch("https://api.github.com/users/thiaaagao/repos?sort=updated&per_page=8")
    const data = await res.json()
    const featuredNames = new Set(featured.map(f => f.title))
    apiProjetos.value = data
      .filter(r => !r.fork && !featuredNames.has(r.name))
      .map(r => ({
        title: r.name,
        desc: r.description || "Sem descrição",
        stack: r.language ? [r.language] : [],
        gitUrl: r.html_url,
        liveUrl: r.homepage || null,
        icon: "ph-code-block"
      }))
  } catch (e) {
    console.error("Erro ao buscar repos:", e)
  } finally {
    loading.value = false
  }
})
</script>

<template>
  <section class="section" id="projetos">
    <div class="container">
      <h2 class="section-title">Projetos</h2>

      <div v-if="loading" class="proj-loading">
        <i class="ph-circle-notch" style="font-size: 2rem; animation: spin 1s linear infinite;"></i>
        <p>Carregando projetos...</p>
      </div>

      <template v-else>
        <h3 class="proj-subtitle"><i class="ph-star"></i> Destaques</h3>
        <div class="proj-grid proj-grid-featured">
          <div class="glass projeto-card featured" v-for="p in featured" :key="p.title">
            <div class="proj-body">
              <div class="proj-head">
                <i :class="p.icon" style="font-size: 2rem; color: var(--accent);"></i>
                <span class="featured-badge">Destaque</span>
              </div>
              <div class="proj-stack">
                <span class="proj-badge" v-for="tech in p.stack" :key="tech">{{ tech }}</span>
              </div>
              <h3 class="proj-title">{{ p.title }}</h3>
              <p class="proj-desc">{{ p.desc }}</p>
              <div class="proj-links">
                <a :href="p.gitUrl" target="_blank" rel="noopener noreferrer" class="btn btn-glass btn-sm">
                  <i class="ph-github-logo"></i> Código
                </a>
                <a v-if="p.liveUrl" :href="p.liveUrl" target="_blank" rel="noopener noreferrer" class="btn btn-primary btn-sm">
                  <i class="ph-globe"></i> Live
                </a>
              </div>
            </div>
          </div>
        </div>

        <div v-if="apiProjetos.length" style="margin-top: 48px;">
          <h3 class="proj-subtitle"><i class="ph-github-logo"></i> Mais projetos</h3>
          <div class="proj-grid">
            <div class="glass projeto-card" v-for="p in apiProjetos" :key="p.title">
              <div class="proj-body">
                <i :class="p.icon" style="font-size: 2rem; color: var(--accent);"></i>
                <div class="proj-stack">
                  <span class="proj-badge" v-for="tech in p.stack" :key="tech">{{ tech }}</span>
                </div>
                <h3 class="proj-title">{{ p.title }}</h3>
                <p class="proj-desc">{{ p.desc }}</p>
                <div class="proj-links">
                  <a :href="p.gitUrl" target="_blank" rel="noopener noreferrer" class="btn btn-glass btn-sm">
                    <i class="ph-github-logo"></i> Código
                  </a>
                  <a v-if="p.liveUrl" :href="p.liveUrl" target="_blank" rel="noopener noreferrer" class="btn btn-primary btn-sm">
                    <i class="ph-globe"></i> Live
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </template>

      <div class="proj-footer">
        <a href="https://github.com/thiaaagao?tab=repositories" target="_blank" rel="noopener noreferrer" class="btn btn-glass">
          <i class="ph-github-logo"></i> Ver todos no GitHub
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.proj-subtitle {
  font-family: var(--font-title);
  font-size: 1.1rem;
  color: var(--text-secondary);
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 8px;
  letter-spacing: 1px;
}

.proj-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

.proj-grid-featured {
  grid-template-columns: repeat(3, 1fr);
}

.projeto-card {
  padding: 0;
  display: flex;
  flex-direction: column;
  overflow: hidden;
}

.projeto-card.featured {
  border-color: var(--accent-dim);
  background: rgba(34, 211, 238, 0.04);
}

.proj-body {
  padding: 28px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  flex: 1;
}

.proj-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.featured-badge {
  background: var(--accent);
  color: var(--bg-primary);
  font-size: 0.7rem;
  font-weight: 700;
  padding: 3px 10px;
  border-radius: 100px;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.proj-stack {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.proj-badge {
  background: var(--accent-dim);
  color: var(--accent);
  padding: 4px 12px;
  border-radius: 100px;
  font-size: 0.75rem;
  font-weight: 500;
}

.proj-title {
  font-family: var(--font-title);
  font-size: 1.1rem;
  color: var(--text-primary);
  font-weight: 500;
  letter-spacing: 1px;
}

.proj-desc {
  font-size: 0.9rem;
  color: var(--text-muted);
  line-height: 1.6;
  flex: 1;
}

.proj-links {
  display: flex;
  gap: 8px;
  margin-top: 8px;
}

.btn-sm {
  padding: 6px 14px;
  font-size: 0.8rem;
}

.proj-loading {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
  padding: 48px 0;
  color: var(--text-muted);
}

.proj-footer {
  text-align: center;
  margin-top: 32px;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

@media (max-width: 1024px) {
  .proj-grid-featured {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .proj-grid,
  .proj-grid-featured {
    grid-template-columns: 1fr;
  }
}
</style>
