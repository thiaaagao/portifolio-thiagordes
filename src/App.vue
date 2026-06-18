<script setup>
import { ref, onMounted, onUnmounted } from "vue"
import NavbarComp from "./components/NavbarComp.vue"
import HeroSection from "./components/HeroSection.vue"
import SobreSection from "./components/SobreSection.vue"
import HabilidadesSection from "./components/HabilidadesSection.vue"
import ServicosSection from "./components/ServicosSection.vue"
import ProjetosSection from "./components/ProjetosSection.vue"
import AsatechSection from "./components/AsatechSection.vue"
import ContatoSection from "./components/ContatoSection.vue"

const scrolled = ref(false)

function handleScroll() {
  scrolled.value = window.scrollY > 50
}

let observer = null

onMounted(() => {
  window.addEventListener("scroll", handleScroll)

  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("visible")
        }
      })
    },
    { threshold: 0.1 }
  )

  document.querySelectorAll(".section, .hero, .footer, .glass, .contato-item, .projeto-card, .servico-card").forEach((el) => {
    observer.observe(el)
  })
})

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll)
  if (observer) observer.disconnect()
})
</script>

<template>
  <NavbarComp :scrolled="scrolled" />
  <HeroSection />
  <SobreSection />
  <HabilidadesSection />
  <ServicosSection />
  <ProjetosSection />
  <AsatechSection />
  <ContatoSection />
  <footer class="footer section" style="padding: 40px 0; text-align: center;">
    <div class="container">
      <p style="color: var(--text-muted); font-size: 0.9rem;">
        &copy; 2026 Thiago Rodrigues &mdash; Feito com <span style="color: #ef4444;">&hearts;</span> e c&oacute;digo
      </p>
    </div>
  </footer>
</template>
