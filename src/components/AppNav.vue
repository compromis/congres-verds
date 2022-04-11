<template>
  <nav class="nav">
    <a href="https://verds.compromis.net" target="_blank" class="logo-verds">
      <img src="@/images/logo-verds.svg" alt="Verds-Equo">
    </a>
    <a href="https://compromis.net" target="_blank" class="logo-compromis">
      <CompromisLogo mono />
    </a>
    <a href="https://europeangreens.eu/" target="_blank" class="logo-eg">
      <img src="@/images/logo-eg.svg" alt="European Greens">
    </a>
  </nav>
</template>

<script setup>
import CompromisLogo from '@compromis/blobby/components/logos/CompromisLogo.vue'
</script>

<style lang="scss" scoped>
.nav {
  position: fixed;
  display: flex;
  padding: 1rem;
  align-items: center;
  top: 0;
  left: 0;
  right: 0;

  .logo-verds {
    img {
      height: 2rem;
    }
  }

  .logo-compromis {
    margin-left: auto;
    color: var(--white);

    :deep(svg) {
      height: 1.5rem;
    }
  }

  .logo-eg {
    img {
      height: 3rem;
      margin-left: 1rem;
    }
  }
}
</style>