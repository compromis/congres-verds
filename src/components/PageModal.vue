<template>
  <article class="page-modal">
    <header class="page-header">
      <h2>{{ title }}</h2>
      <button class="close" @click="$emit('close')">
        <CloseIcon />
      </button>
    </header>
    <section class="page-content">
      <slot />
    </section>
  </article>
</template>

<script setup>
import CloseIcon from './CloseIcon.vue'

defineProps({
  title: {
    type: String,
    required: true,
  }
})
</script>

<style lang="scss">
.page-modal {
  position: absolute;
  top: 6rem;
  right: 3rem;
  background: var(--white);
  color: var(--black);
  width: 100%;
  max-width: 500px;
  padding: 2rem;
  border-radius: 1.5rem;
  box-shadow: var(--shadow-default);
  z-index: 100;
}

.page-header {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
  gap: .5rem;

  h2 {
    color: var(--green);
    font-family: var(--font-headings);
    font-weight: bold;
  }

  button {
    appearance: none;
    background: transparent;
    border: 0;
    margin-left: auto;
    font-size: 1.5rem;
    padding: 0;
    background: var(--yellow);
    height: 1.75em;
    width: 1.75em;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 100%;
    line-height: 1;
    margin-top: -.5em;
    color: var(--black);
    flex-shrink: 0;

    svg {
      height: 1em;
      width: 1em;
    }

    &:hover {
      background: var(--green);
      color: var(--white);
    }
  }
}

.page-content {
  font-size: 1.5rem;
}

@media (max-width: 750px) {
  .page-modal {
    position: fixed;
    top: auto;
    bottom: 2rem;
    left: 1rem;
    right: 1rem;
    width: auto;
    max-height: 80vh;
    overflow: auto;
    z-index: 100000;
  }
}
</style>