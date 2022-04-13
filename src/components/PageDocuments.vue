<script setup>
import DocumentIcon from './DocumentIcon.vue'
</script>

<template>
  <ul class="docs">
    <li>
      <a href="https://valencia.discuss.green/valencia/estatuts-vqpv-2016-12865" target="_blank">
        <DocumentIcon />
        Ponència Estatuts
      </a>
    </li>
    <li>
      <a href="https://valencia.discuss.green/valencia/las-propuestas-verdes-a-los-retos-de-la-ciudadania-valenciana-para-el-482" target="_blank">
        <DocumentIcon />
        Ponència Política
      </a>
    </li>
    <li>
      <a href="https://valencia.discuss.green/valencia/reglament-del-iiier-congres-de-verds-equo-del-pais-valencia-7-de-maig-4838" target="_blank">
        <DocumentIcon />
        Reglament congressual
      </a>
    </li>
  </ul>
</template>

<style lang="scss" scoped>
.docs {
  list-style: none;
  margin: 0;
  padding: 0;

  a {
    display: flex;
    color: var(--black);
    align-items: center;

    svg {
      height: 1.5rem;
      width: 1.5rem;
      margin-right: .5rem;
    }
  }
}
</style>