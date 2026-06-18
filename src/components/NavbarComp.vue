<script setup>
import { ref } from "vue"

defineProps({
  scrolled: Boolean
})

const menuOpen = ref(false)

function toggleMenu() {
  menuOpen.value = !menuOpen.value
}

function closeMenu() {
  menuOpen.value = false
}
</script>

<template>
  <nav :class="['navbar', { scrolled }]">
    <div class="navbar-container">
      <a href="#" class="navbar-logo" @click="closeMenu">TR</a>
      <button class="navbar-toggle" @click="toggleMenu" aria-label="Menu">
        <i :class="menuOpen ? 'ph-x' : 'ph-list'"></i>
      </button>
      <ul :class="['navbar-links', { open: menuOpen }]">
        <li><a href="#sobre" @click="closeMenu">Sobre</a></li>
        <li><a href="#habilidades" @click="closeMenu">Habilidades</a></li>
        <li><a href="#servicos" @click="closeMenu">Serviços</a></li>
        <li><a href="#projetos" @click="closeMenu">Projetos</a></li>
        <li><a href="#asatech" @click="closeMenu">Asatech</a></li>
        <li><a href="#contato" @click="closeMenu">Contato</a></li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 16px 0;
  transition: background 0.3s, backdrop-filter 0.3s, border-color 0.3s;
}

.navbar.scrolled {
  background: rgba(10, 10, 15, 0.85);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border-glass);
}

.navbar-container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 20px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.navbar-logo {
  font-family: var(--font-title);
  font-size: 1.5rem;
  color: var(--accent);
  font-weight: 600;
  letter-spacing: 2px;
}

.navbar-links {
  display: flex;
  gap: 32px;
}

.navbar-links a {
  font-family: var(--font-title);
  font-size: 0.85rem;
  color: var(--text-secondary);
  letter-spacing: 1px;
  transition: color 0.3s;
  font-weight: 500;
}

.navbar-links a:hover {
  color: var(--accent);
}

.navbar-toggle {
  display: none;
  background: none;
  border: none;
  color: var(--text-primary);
  font-size: 1.5rem;
  cursor: pointer;
}

@media (max-width: 768px) {
  .navbar-toggle {
    display: block;
  }

  .navbar-links {
    display: none;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    flex-direction: column;
    background: rgba(10, 10, 15, 0.95);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border-glass);
    padding: 20px;
    gap: 16px;
    text-align: center;
  }

  .navbar-links.open {
    display: flex;
  }
}
</style>
