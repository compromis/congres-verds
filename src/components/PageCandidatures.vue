<script setup>
import DocumentIcon from './DocumentIcon.vue'
</script>

<template>
  <p>El termini de presentació de candidatures encara està obert.</p>
  <p>Termini de presentació: <strong>1 de maig 2022</strong>.</p>
  <h3>Candidatures presentades</h3>
  <ul class="docs">
    <li>
      <a href="/docs/resposta-verda.pdf" target="_blank">
        <DocumentIcon />
        Resposta Verda
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