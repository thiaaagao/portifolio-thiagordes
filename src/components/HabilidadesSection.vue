<script setup>
const skillCategories = [
  {
    title: "Infra & Ciberseguran\u00e7a",
    icon: "ph-shield-check",
    skills: ["Active Directory", "Azure AD", "VPN", "Zabbix", "Grafana", "GLPI", "FreePBX", "SIEM", "IAM", "OWASP", "LGPD"]
  },
  {
    title: "Desenvolvimento",
    icon: "ph-code",
    skills: ["Python", "JavaScript/TypeScript", "React", "Vue 3", "Flutter", "HTML/CSS", "SQL", "API REST"]
  },
  {
    title: "Ferramentas",
    icon: "ph-wrench",
    skills: ["Power BI", "Jira", "Notion", "Miro", "Figma", "Postman", "Git"]
  }
]

const highlight = {
  title: "Ciberseguran\u00e7a",
  icon: "ph-crown",
  skills: ["An\u00e1lise de Vulnerabilidades", "Resposta a Incidentes", "SOC N1/N2", "Threat Intelligence"]
}
</script>

<template>
  <section class="section" id="habilidades">
    <div class="container">
      <h2 class="section-title">Habilidades</h2>
      <div class="hab-grid">
        <div class="glass hab-card" v-for="cat in skillCategories" :key="cat.title">
          <div class="hab-header">
            <i :class="cat.icon" style="font-size: 1.5rem; color: var(--accent);"></i>
            <h3 class="hab-title">{{ cat.title }}</h3>
          </div>
          <div class="hab-tags">
            <span class="hab-tag" v-for="skill in cat.skills" :key="skill">{{ skill }}</span>
          </div>
        </div>
      </div>
      <div class="glass hab-card hab-highlight" style="margin-top: 24px;">
        <div class="hab-header">
          <i class="ph-crown" style="font-size: 1.5rem; color: var(--accent);"></i>
          <h3 class="hab-title">{{ highlight.title }}</h3>
        </div>
        <div class="hab-tags">
          <span class="hab-tag" v-for="skill in highlight.skills" :key="skill">{{ skill }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hab-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}

.hab-card {
  padding: 28px;
}

.hab-highlight {
  border-color: var(--accent-dim);
  background: rgba(34, 211, 238, 0.06);
}

.hab-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 20px;
}

.hab-title {
  font-family: var(--font-title);
  font-size: 1rem;
  color: var(--text-primary);
  font-weight: 500;
  letter-spacing: 1px;
}

.hab-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.hab-tag {
  background: var(--accent-dim);
  color: var(--accent);
  padding: 6px 14px;
  border-radius: 100px;
  font-size: 0.8rem;
  font-weight: 500;
}

@media (max-width: 768px) {
  .hab-grid {
    grid-template-columns: 1fr;
  }
}
</style>
